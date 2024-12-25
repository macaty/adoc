[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 生成 DLL

```aardio aardio
//生成 DLL

var basic  = /***
'源码使用 UTF-8 编码
#define UNICODE

'引用头文�?#include "windows.bi"

'声明一个结构体类型，类�?aardio 里的 class
type INFO_STRUCT
 x as LONG
 y as ULong
end type

'声明一个结构体指针，aardio 里结构体全部是指针，所以不需要单独声�?type LPINFO as INFO_STRUCT ptr

'导出函数最好是放到 Extern 'C' 里，不然要写 Alias 指定导出函数名是比较麻烦的�?Extern "C"
   '一个DLL里必须要�?个输出，就是在函数后面加 Export
   '要对别注意一�?Long �?aardio 中的类型�?int，�?ULong �?aardio 中的类型是大写的 INT
   Function msgboxW(ByVal longVal As Long,ByVal ulongVal As ULong,byval strVal as LPCWSTR ,ByVal structVal as LPINFO) As Long Export
      '如果在函数名后加一个大写的W,aardio aardio 默认会传 UTF16 编码的字符串，否则会�?UTF8 编码的字符串�?      MessageBox(0,strVal,"",0)

      'structVal 实际上是一个结构体指针，所以要用指针操作符 -> 访问结构体成�?      structVal->x = longVal
      structVal->y = ulongVal

      return 1
   End Function
End Extern
***/
string.save("/basic.bas", basic)

import console;
import process.freeBasic;

console.open();
process.freeBasic.dll("/basic.bas").wait();

/*
FreeBASIC 的运行库基于 LGPLv2 开源许可证 - 并且额外允许静态链接，
所以使用FreeBASIC生成独立的执行文件，无须再以GPL开源，可以自由使用�?*/
console.pause(,"已生成DLL，按任意键退出�?);
io.remove("/libbasic.dll.a");

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/FreeBASIC/dll.md)

