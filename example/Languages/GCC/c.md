[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 GCC �?C 语言

```aardio aardio
//aardio 调用 GCC �?C 语言
import process.gcc;

//创建 GCC 环境，参数指�?C/C++ 源码目录
var gcc = process.gcc("/");
//C语言语法速览 https://quickref.me/zh-CN/docs/c.html

//自动存为 main.c
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

//生成 DLL。参数：-shared 生成 DLL�?s 移除调试符号减小体积�?-municode 启用 Unicode
gcc.exec("main.c -o c.dll -shared -s -municode -m32 -O2 -static -lgcc -lstdc++")

//加载 DLL，默认使�?cdecl 调用约定
var dll = raw.loadDll("c.dll",,"cdecl");

/*
调用 DLL，带 W 尾标�?API 传入 UTF-8 字符串时自动转换�? Unicode（UTF-16�?字符�?https://www.aardio.com/zh-cn/doc/library-guide/builtin/raw/directCall.html
*/
dll.TestW("测试 UTF-8 自动�?Unicode（UTF-16�?字符�?);

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/GCC/c.md)

