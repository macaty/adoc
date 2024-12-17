[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 璋冪敤 GCC 涔?C 璇█

```aardio aardio
//aardio 璋冪敤 GCC 涔?C 璇█
import process.gcc;

//鍒涘缓 GCC 鐜锛屽弬鏁版寚瀹?C/C++ 婧愮爜鐩綍
var gcc = process.gcc("/");
//C璇█璇硶閫熻 https://quickref.me/zh-CN/docs/c.html

//鑷姩瀛樹负 main.c
gcc.main = /*************
#include <windows.h>

int __stdcall DllMain(void * hinstDLL, unsigned long fdwReason, void * lpvReserved) {

    if (fdwReason == DLL_PROCESS_ATTACH){

    }
    return 1;
}

__declspec(dllexport) int TestW (const wchar_t* txt)
{
    MessageBox(0,txt,u"GCC",0);
}
*************/

//鐢熸垚 DLL銆傚弬鏁帮細-shared 鐢熸垚 DLL锛?s 绉婚櫎璋冭瘯绗﹀彿鍑忓皬浣撶Н锛?-municode 鍚敤 Unicode
gcc.exec("main.c -o c.dll -shared -s -municode -m32 -O2 -static -lgcc -lstdc++")

//鍔犺浇 DLL锛岄粯璁や娇鐢?cdecl 璋冪敤绾﹀畾
var dll = raw.loadDll("c.dll",,"cdecl");

/*
璋冪敤 DLL锛屽甫 W 灏炬爣鐨?API 浼犲叆 UTF-8 瀛楃涓叉椂鑷姩杞崲涓? Unicode锛圲TF-16锛?瀛楃涓?https://www.aardio.com/zh-cn/doc/library-guide/builtin/raw/directCall.html
*/
dll.TestW("娴嬭瘯 UTF-8 鑷姩杞?Unicode锛圲TF-16锛?瀛楃涓?);

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/GCC/c.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/GCC/c.md')

