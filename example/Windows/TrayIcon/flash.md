[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 托盘图标跳动

```aardio aardio
//托盘图标跳动
import win.ui;
/*DSG{{*/
var winform = win.form(text="托盘图标跳动";right=759;bottom=469)
winform.add(
button={cls="button";text="停止";left=386;top=250;right=534;bottom=339;z=1}
)
/*}}*/

import win.util.tray;
var tray = win.util.tray(winform,hIcon);
var hIcon = ::LoadIcon(null, topointer(0x7F00/*_IDI_APPLICATION*/));

winform.reduce( { hIcon;},
    function(value,index){
        tray.icon = value;
        return 500;
    }
)

winform.button.oncommand = function(id,event){
    winform.reduce(false);
    tray.icon = hIcon;
}

winform.show()
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/TrayIcon/flash.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/TrayIcon/flash.md')

