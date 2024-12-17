[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: thiscall

```aardio aardio
//DLL / thiscall
import vc6;

var vc = vc6( "/" );

//杈撳叆 C++ 婧愮爜锛岃嚜鍔ㄤ繚瀛樹负鍚屽悕鏂囦欢 /main.cpp
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
******/

//缂栬瘧鐢熸垚DLL
vc.exec(
    'cl main.cpp'
    ,'/W3' /*璀﹀憡绛夌骇*/
    ,'/MD' /*浣跨敤澶氱嚎绋嬪姩鎬佽繍琛屽簱*/
    ,'/O2 /Ot /EHsc' /*浠ｇ爜浼樺寲閫夐」*/
    ,'/D "WIN32" /D "_WINDOWS" /D "_MBCS" /D "_USRDLL"' /*瀹氫箟甯告暟鍜屽畯*/
    ,'/I"./INCLUDE"'/*鎸囧畾澶存枃浠剁洰褰?/
    ,'kernel32.lib user32.lib gdi32.lib winspool.lib comdlg32.lib advapi32.lib shell32.lib ole32.lib oleaut32.lib uuid.lib odbc32.lib odbccp32.lib' /*瀵煎叆搴?/
    ,'/link /SUBSYSTEM:WINDOWS /MACHINE:X86' /*鍚庨潰鏄摼鎺ュ弬鏁?*/
    ,'/out:thiscall.dll'/*杈撳嚭鏂囦欢鍚?/
    ,'/dll' /*杈撳嚭DLL*/
    ,'/LIBPATH:".\LIB" /LIBPATH:".\LIB2"' /*鎸囧畾搴撶洰褰?/
)

var dll = raw.loadDll("/thiscall.dll",,"cdecl");

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

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/CPP/thiscall.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/CPP/thiscall.md')

