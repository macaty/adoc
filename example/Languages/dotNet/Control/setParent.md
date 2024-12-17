[aardio 鏂囨。](../../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 宓屽叆 .NET 绐楀彛

```aardio aardio
//aardio 宓屽叆 .NET 绐楀彛
import dotNet;
var compiler = dotNet.createCompiler("C#");
compiler.Reference("System.Drawing.dll","System.Data.dll","System.Windows.Forms.dll");
compiler.addSource("/0.WindowsFormsApp1.cs");
compiler.import("WindowsFormsApp1");

import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio form";right=1047;bottom=634;bgcolor=10789024)
winform.add(
custom={cls="custom";text="鑷畾涔夋帶浠?;left=26;top=23;right=799;bottom=416;bgcolor=16777215;db=1;dl=1;dr=1;dt=1;z=1}
)
/*}}*/

var netform = WindowsFormsApp1.Form1();

//涓嬮潰杩欎竴鍙ュ皢 .NET 绐楀彛宓屽叆 aardio 绐楀彛銆?dotNet.setParent(netform,winform.custom);

//娣诲姞 .NET 濮旀墭鍥炶皟
netform.onButton1Click = function(){
    winform.msgbox("鐐瑰嚮浜?C# 鍦?aardio 绐楀彛閲屽垱寤虹殑鎸夐挳锛屽湪 C# 涓皟鐢?aardio 鍑芥暟銆?);
    netform.button1.Text = "鐐瑰嚮浜?C# 鍒涘缓鐨勬寜閽?;
}

winform.show();
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/Control/setParent.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/Control/setParent.md')

