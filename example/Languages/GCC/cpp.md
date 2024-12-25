[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 GCC �?C++

```aardio aardio
//aardio 调用 GCC �?C++
import process.gcc;

//创建 GCC 环境，参数指�?C/C++ 源码目录
var gcc = process.gcc("/");
//C++语法速览 https://quickref.me/zh-CN/docs/cpp.html

//自动存为 main.cpp
gcc["main.cpp"] = /*************
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
*************/

//生成 DLL。参数：-shared 生成 DLL�?s 移除调试符号减小体积�?-municode 启用 Unicode
gcc.exec("main.cpp -o cpp.dll -shared -s -municode -m32 -O2 -static -lgcc -lstdc++");

//也可以调�?gcc.exe 同目录的其他 exe，g++,make 可以省略 .exe 后缀�?//gcc.exec("g++ main.cpp -o cpp.dll -shared -s -municode -m32 -O2 -static -lgcc -lstdc++");

var dll = raw.loadDll("/cpp.dll",,"cdecl");

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

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/GCC/cpp.md)

