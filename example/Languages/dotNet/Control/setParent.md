[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 嵌入 .NET 窗口

```aardio aardio
//aardio 嵌入 .NET 窗口
import dotNet;
var compiler = dotNet.createCompiler("C#");
compiler.Reference("System.Drawing.dll","System.Data.dll","System.Windows.Forms.dll");
compiler.addSource("/0.WindowsFormsApp1.cs");
compiler.import("WindowsFormsApp1");

import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio form";right=1047;bottom=634;bgcolor=10789024)
winform.add(
custom={cls="custom";text="自定义控�?;left=26;top=23;right=799;bottom=416;bgcolor=16777215;db=1;dl=1;dr=1;dt=1;z=1}
)
/*}}*/

var netform = WindowsFormsApp1.Form1();

//下面这一句将 .NET 窗口嵌入 aardio 窗口�?dotNet.setParent(netform,winform.custom);

//添加 .NET 委托回调
netform.onButton1Click = function(){
    winform.msgbox("点击�?C# �?aardio 窗口里创建的按钮，在 C# 中调�?aardio 函数�?);
    netform.button1.Text = "点击�?C# 创建的按�?;
}

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/Control/setParent.md)

