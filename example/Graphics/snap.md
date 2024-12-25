[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 前台、后台截�?
```aardio aardio
//前台、后台截�?import win.ui;
/*DSG{{*/
var winform = win.form(text="抓屏演示";right=727;bottom=370;topmost=1)
winform.add(
listbox={cls="listbox";left=14;top=10;right=325;bottom=333;bgcolor=16777215;db=1;dl=1;dt=1;edge=1;items={};z=1};
picturebox={cls="plus";left=338;top=15;right=706;bottom=336;center=1;db=1;dl=1;dr=1;dt=1;mode="scale";repeat="scale";transparent=1;z=2};
radioPrint={cls="radiobutton";text="后台抓图";left=372;top=342;right=459;bottom=361;db=1;dr=1;z=4};
radioPrintClient={cls="radiobutton";text="后台抓图(客户�?";left=473;top=342;right=613;bottom=361;db=1;dr=1;z=6};
radioSnap={cls="radiobutton";text="前台抓屏";left=149;top=342;right=227;bottom=362;checked=1;db=1;dr=1;z=3};
radioSnapClient={cls="radiobutton";text="前台抓屏(客户�?";left=241;top=342;right=359;bottom=362;db=1;dr=1;z=5};
static={cls="static";text="双击上面的窗口抓�?;left=21;top=343;right=139;bottom=360;db=1;dr=1;transparent=1;z=7}
)
/*}}*/

winform.listbox.hwndList = {};

import winex;
winex.enumTop(
    function (hwnd) {
        if( ! win.isVisible(hwnd) ) return;
        var title = winex.getText(hwnd);
        if (#title && title!="Program Manager") {
           winform.listbox.add(title)
           winform.listbox.hwndList[ winform.listbox.count ] = hwnd;
        }
    }
);

import gdip.snap;
import win.dlg.message;
winform.listbox.onSelChange = function(){
    if(winform.listbox.selIndex>0){
        var idx = winform.listbox.selIndex
        var hwnd = winform.listbox.hwndList[idx];

        var picture;
        if( hwnd ){
            if( winform.radioSnap.checked ){
                winform.show( false )
                picture = gdip.snap(hwnd)
                winform.show( 0x1/*_SW_SHOWNORMAL*/ )
            }
            elseif( winform.radioSnapClient.checked ){
                winform.show( false )
                picture = gdip.snap.client(hwnd)
                winform.show( 0x1/*_SW_SHOWNORMAL*/ )
            }
            elseif( winform.radioPrint.checked ){
                picture = gdip.snap.print( hwnd )
            }
            elseif( winform.radioPrintClient.checked ){
                picture = gdip.snap.printClient(hwnd)
            }

            if(picture){
                winform.picturebox.background = picture
            }
            else {
                winform.msgFrown("截图失败")
            }
        }
    }
}

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Graphics/snap.md)

