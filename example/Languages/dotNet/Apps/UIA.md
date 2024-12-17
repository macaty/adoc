[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 使用 .NET 调用 UIA 接口

```aardio aardio
//使用 .NET 调用 UIA 接口
//探测工具  file://~/tools/Spy/inspect.aardio

//运行程序
import process;
process.execute("notepad.exe",{io.getSpecial(0x25/*_CSIDL_SYSTEM*/,"drivers\etc\HOSTS")});

//等待激活的窗口句柄，文本框句柄
import winex;
var hwnd,hEdit = winex.waitActive(,,"Notepad"
    ,"<RichEditD2DPT>|<Edit>");//模式语法：类名为 RichEditD2DPT �?Edit

//导入 .NET �?//https://learn.microsoft.com/zh-cn/dotnet/api/system.windows.automation?view=netframework-4.6
import System.Windows.Automation;//通过 UIAutomationClient 加载
//改为 import System.Windows.Automation.3 可支�?TextPattern2 等接口，下面的代码不必更改�?
//访问 .NET 类的静态成�?Automation = System.Windows.Automation;

//查找写字板窗口。由 System.Windows.Automation.And 生成查询条件�?var wordpad = Automation.FindByAnd({
    ClassName = "Notepad",
    ControlType = "Window";
})

if(!wordpad) error("未发现目标窗�?);

//查找写字板的编辑框。由 System.Windows.Automation.Or 生成查询条件�?var editBox = Automation.FindByOr({
    ClassName = {"RichEditD2DPT","RICHEDIT50W","Edit" }
},wordpad)

var hwnd = editBox.Current.NativeWindowHandle;//窗口句柄

//鼠标操作，移动鼠标到控件位置
import mouse;
mouse.moveTo(editBox.Current.BoundingRectangle);

//获取写字板内的文�?//https://learn.microsoft.com/en-us/dotnet/api/system.windows.automation.textpattern?view=netframework-4.0
var textPattern;
try {
    //获取 Pattern 失败会抛出异�?    textPattern = editBox.GetCurrentPattern(Automation.TextPattern.Pattern);
}

import win.dlg.message;
if(textPattern){
    var text = textPattern.DocumentRange.GetText(50);
    win.dlg.message().info(text + " …�?);
}
else{
    return win.dlg.message().info("写字板文本框句柄�? + hwnd)
}

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/Apps/UIA.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/Apps/UIA.md')

