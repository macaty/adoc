[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 运行 C++

```aardio aardio
//运行 C++
import vc6;
import console;

/*
C++ 快速入�?https://quickref.me/zh-CN/docs/cpp.html
https://learnxinyminutes.com/docs/zh-cn/c++-cn
*/
console.showLoading(" 正在加载 C++ 代码");
var dll = vc6.loadcode(`
#define _WIN32_WINNT 0x0501
#include <winsock2.h>
#include <Ws2tcpip.h>
#pragma comment(lib, "ws2_32.lib")
#include <windows.h>
#include <stdio.h>
#include <stdlib.h>
#include <windows.h>
#include <winuser.h>
#include <basetsd.h>
#include <basetyps.h>
#include <winbase.h>
#include <wincon.h>
#include <windef.h>
#include <windows.h>
#include <winerror.h>
#include <wingdi.h>
#include <winnls.h>
#include <winnt.h>
#include <winreg.h>
#include <winuser.h>
#include <winver.h>
#include <winioctl.h>
#include <Commctrl.h>
#define DllExport __declspec( dllexport )

extern "C" {
    DllExport int __cdecl getValue() {
        return CTL_CODE(IOCTL_STORAGE_BASE, 0x0500, METHOD_BUFFERED, FILE_ANY_ACCESS);
    }
}`);

//https://www.aardio.com/zh-cn/doc/library-guide/builtin/raw/directCall.html
var value = dll.getValue();
var str = string.format("0x%X",value);
console.log("已复�? " + str,value);

import win.clip;
win.clip.write(str);

console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/CPP/vc6.loadcode.md)

