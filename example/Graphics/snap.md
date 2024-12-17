[aardio 鏂囨。](../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鍓嶅彴銆佸悗鍙版埅灞?
```aardio aardio
//鍓嶅彴銆佸悗鍙版埅灞?import win.ui;
/*DSG{{*/
var winform = win.form(text="鎶撳睆婕旂ず";right=727;bottom=370;topmost=1)
winform.add(
listbox={cls="listbox";left=14;top=10;right=325;bottom=333;bgcolor=16777215;db=1;dl=1;dt=1;edge=1;items={};z=1};
picturebox={cls="plus";left=338;top=15;right=706;bottom=336;center=1;db=1;dl=1;dr=1;dt=1;mode="scale";repeat="scale";transparent=1;z=2};
radioPrint={cls="radiobutton";text="鍚庡彴鎶撳浘";left=372;top=342;right=459;bottom=361;db=1;dr=1;z=4};
radioPrintClient={cls="radiobutton";text="鍚庡彴鎶撳浘(瀹㈡埛鍖?";left=473;top=342;right=613;bottom=361;db=1;dr=1;z=6};
radioSnap={cls="radiobutton";text="鍓嶅彴鎶撳睆";left=149;top=342;right=227;bottom=362;checked=1;db=1;dr=1;z=3};
radioSnapClient={cls="radiobutton";text="鍓嶅彴鎶撳睆(瀹㈡埛鍖?";left=241;top=342;right=359;bottom=362;db=1;dr=1;z=5};
static={cls="static";text="鍙屽嚮涓婇潰鐨勭獥鍙ｆ姄灞?;left=21;top=343;right=139;bottom=360;db=1;dr=1;transparent=1;z=7}
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
                winform.msgFrown("鎴浘澶辫触")
            }
        }
    }
}

winform.show();
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Graphics/snap.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Graphics/snap.md')

