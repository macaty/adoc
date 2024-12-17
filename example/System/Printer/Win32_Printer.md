[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 查找打印�?
```aardio aardio
//查找打印�?/*
//添加网络打印�?var network = com.CreateObject("WScript.Network")
network.AddWindowsPrinterConnection "\\IP地址或主机名\打印机名"

//参考：
%windir%/System32/Printing_Admin_Scripts/zh-CN
https://learn.microsoft.com/zh-cn/windows/win32/cimwin32prov/win32-printer
*/

import console
import com.wmi;

for index,printer in com.wmi.each("Select * From Win32_Printer") {

    console.log(printer.Name,printer.Network?"网络打印�?:"本地打印�?);

    com.Release(printer);
}

/*
网络打印机可参考�?aardio 工具 > 网络管理 > 端口扫描 / 端口检�?』源码�?*/

console.pause(true);

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/System/Printer/Win32_Printer.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/System/Printer/Win32_Printer.md')

