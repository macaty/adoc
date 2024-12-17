[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 杩愯 C++

```aardio aardio
//杩愯 C++
import vc6;
import console;

/*
C++ 蹇�熷叆闂?https://quickref.me/zh-CN/docs/cpp.html
https://learnxinyminutes.com/docs/zh-cn/c++-cn
*/
console.showLoading(" 姝ｅ湪鍔犺浇 C++ 浠ｇ爜");
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
console.log("宸插鍒? " + str,value);

import win.clip;
win.clip.write(str);

console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/CPP/vc6.loadcode.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/CPP/vc6.loadcode.md')

