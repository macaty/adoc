[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 璋冪敤 GCC 涔?C++

```aardio aardio
//aardio 璋冪敤 GCC 涔?C++
import process.gcc;

//鍒涘缓 GCC 鐜锛屽弬鏁版寚瀹?C/C++ 婧愮爜鐩綍
var gcc = process.gcc("/");
//C++璇硶閫熻 https://quickref.me/zh-CN/docs/cpp.html

//鑷姩瀛樹负 main.cpp
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
    //娉ㄦ剰鍑芥暟澹版槑鍓嶅姞涓?virtual 浠ユ敮鎸?aardio 涓殑 raw.interface
    virtual void getName(char *buffer,int len);
    virtual void getInfo(TestInfo *pInfo);
};

void CTestObject::getName(char *buffer,int len){
    strcpy(buffer,"娴嬭瘯");
}

void CTestObject::getInfo(TestInfo *pInfo){
    pInfo->x = 1;
    pInfo->y = 2;
    strcpy((char *)pInfo->name,"娴嬭瘯");
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

//鐢熸垚 DLL銆傚弬鏁帮細-shared 鐢熸垚 DLL锛?s 绉婚櫎璋冭瘯绗﹀彿鍑忓皬浣撶Н锛?-municode 鍚敤 Unicode
gcc.exec("main.cpp -o cpp.dll -shared -s -municode -m32 -O2 -static -lgcc -lstdc++");

//涔熷彲浠ヨ皟鐢?gcc.exe 鍚岀洰褰曠殑鍏朵粬 exe锛実++,make 鍙互鐪佺暐 .exe 鍚庣紑銆?//gcc.exec("g++ main.cpp -o cpp.dll -shared -s -municode -m32 -O2 -static -lgcc -lstdc++");

var dll = raw.loadDll("/cpp.dll",,"cdecl");

import raw.interface;
class testObject{
    ctor(){
        //鍒涘缓 C++ 瀵硅薄,骞惰幏鍙栨寚閽堬紝娉ㄦ剰杩欓噷浣跨敤浜?P 灏炬爣鑾峰彇鎸囬拡銆?        var pTest = dll.CreateTestObjectP();

        //C++ 瀵硅薄鎸囬拡杞崲涓?aardio 瀵硅薄銆?        this = ..raw.interface( pTest,"
            void getName(string &buffer,int len);
            void getInfo(struct &pInfo);
            ","thiscall" //娉ㄦ剰璋冪敤绾﹀畾涓簍hiscall
        )

        //娣诲姞鏋愭瀯鍑芥暟
        ..table.gc(this,"delete")
    };
    delete = function(){
        if(!owner.deleted){
            dll.DeleteTestObject( owner );
            owner.deleted = true;
        }
    };
}

//鍒涘缓瀵硅薄
var obj = testObject();

//璋冪敤 C++ 鍑芥暟
var name = obj.getName(25,25);
console.log(name);

//璋冪敤 C++ 鍑芥暟
var info = obj.getInfo({ int x;int y;BYTE name[256]})
console.log( info.name  );

console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/GCC/cpp.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/GCC/cpp.md')

