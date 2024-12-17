[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鎵樼洏鍥炬爣璺冲姩

```aardio aardio
//鎵樼洏鍥炬爣璺冲姩
import win.ui;
/*DSG{{*/
var winform = win.form(text="鎵樼洏鍥炬爣璺冲姩";right=759;bottom=469)
winform.add(
button={cls="button";text="鍋滄";left=386;top=250;right=534;bottom=339;z=1}
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

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/TrayIcon/flash.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/TrayIcon/flash.md')

