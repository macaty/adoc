[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 窗口自动�?- 操作窗口菜单

```aardio aardio
//窗口自动�?- 操作窗口菜单
import winex;
import process;
import win.version;

error("代码仅适用传统窗口菜单，Win11 记事本已改版");

var prcs = process("Notepad");
var hwnd = winex.find("Notepad",,prcs.id);
var hEdit = winex.findEx(hwnd,1,"Edit");
winex.sendString("test",hEdit);

//查找指定的菜�? "文件" 菜单下的 "另存�? )
//var hMenu,menuId = winex.findMenu(hwnd ,"文件","另存�?);
//winex.click(hwnd,menuId);

//点击菜单�? "文件" 菜单下的 "另存�? )
winex.click( hwnd,"文件","另存�?)

/*
注意这种方式仅用于点击传统窗口菜单，
无句柄菜单请改用 string.ocrLite �?dotNet.ocr 等屏幕找字组件�?*/

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Automation/Windows/findMenu.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Automation/Windows/findMenu.md')

