[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: thiscall

```aardio aardio
//DLL / thiscall
import vc6;

var vc = vc6( "/" );

//输入 C++ 源码，自动保存为同名文件 /main.cpp
vc.main = /******
#include <windows.h>

struct TestInfo{
    int x;
    int y;
    BYTE name[256];
};

class CTestObject
{
public:
    //注意函数声明前加�?virtual 以支�?aardio 中的 raw.interface
    virtual void getName(char *buffer,int len);
    virtual void getInfo(TestInfo *pInfo);
};

void CTestObject::getName(char *buffer,int len){
    strcpy(buffer,"测试");
}

void CTestObject::getInfo(TestInfo *pInfo){
    pInfo->x = 1;
    pInfo->y = 2;
    strcpy((char *)pInfo->name,"测试");
}

extern "C" __declspec(dllexport) CTestObject* __cdecl CreateTestObject() {
    return new CTestObject();
}

extern "C" __declspec(dllexport) void __cdecl DeleteTestObject( CTestObject* pTest) {
    delete pTest;
}

BOOL WINAPI DllMain(HINSTANCE inst,DWORD reason,LPVOID reserved )
{
    switch( reason )
    {
        case DLL_PROCESS_ATTACH:
            break;

        case DLL_PROCESS_DETACH:
            break;
    }
    return TRUE;
}
******/

//编译生成DLL
vc.exec(
    'cl main.cpp'
    ,'/W3' /*警告等级*/
    ,'/MD' /*使用多线程动态运行库*/
    ,'/O2 /Ot /EHsc' /*代码优化选项*/
    ,'/D "WIN32" /D "_WINDOWS" /D "_MBCS" /D "_USRDLL"' /*定义常数和宏*/
    ,'/I"./INCLUDE"'/*指定头文件目�?/
    ,'kernel32.lib user32.lib gdi32.lib winspool.lib comdlg32.lib advapi32.lib shell32.lib ole32.lib oleaut32.lib uuid.lib odbc32.lib odbccp32.lib' /*导入�?/
    ,'/link /SUBSYSTEM:WINDOWS /MACHINE:X86' /*后面是链接参�?*/
    ,'/out:thiscall.dll'/*输出文件�?/
    ,'/dll' /*输出DLL*/
    ,'/LIBPATH:".\LIB" /LIBPATH:".\LIB2"' /*指定库目�?/
)

var dll = raw.loadDll("/thiscall.dll",,"cdecl");

import raw.interface;
class testObject{
    ctor(){
        //创建 C++ 对象,并获取指针，注意这里使用�?P 尾标获取指针�?        var pTest = dll.CreateTestObjectP();

        //C++ 对象指针转换�?aardio 对象�?        this = ..raw.interface( pTest,"
            void getName(string &buffer,int len);
            void getInfo(struct &pInfo);
            ","thiscall" //注意调用约定为thiscall
        )

        //添加析构函数
        ..table.gc(this,"delete")
    };
    delete = function(){
        if(!owner.deleted){
            dll.DeleteTestObject( owner );
            owner.deleted = true;
        }
    };
}

//创建对象
var obj = testObject();

//调用 C++ 函数
var name = obj.getName(25,25);
console.log(name);

//调用 C++ 函数
var info = obj.getInfo({ int x;int y;BYTE name[256]})
console.log( info.name  );

console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/CPP/thiscall.md)

