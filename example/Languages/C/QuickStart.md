[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 C 语言快速入�?
```aardio aardio
//aardio 调用 C 语言快速入�?//扩展库体积很小，支持发布后生成独�?EXE
import tcc;

/*
C 语言快速入�?https://quickref.me/zh-CN/docs/c.html
https://learnxinyminutes.com/docs/zh-cn/c-cn
*/

//编译 DLL
tcc.build( "/start.dll" ).code = /***
#include <windows.h>
__declspec(dllexport) int Add( int a,int b )
{
    return a + b;
}
***/

//加载 DLL,改为 $"/start.dll" 可将 DLL 嵌入代码，发布后不再需要外�?DLL 文件
var dll = raw.loadDll( "/start.dll",,"cdecl" );

//调用 C函数
var result = dll.Add(12,3);

import win;
win.msgbox(result);

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/C/QuickStart.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/C/QuickStart.md')

