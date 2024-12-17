[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 璁剧疆榧犳爣鎸囬拡锛屽厜鏍囩瓑寰呮晥鏋?
```aardio aardio
//璁剧疆榧犳爣鎸囬拡
import win.ui;
/*DSG{{*/
var winform = win.form(text="璁剧疆榧犳爣鎸囬拡锛屽厜鏍囩瓑寰呮晥鏋?;right=349;bottom=249)
winform.add(
button={cls="button";text="鍏夋爣绛夊緟";left=110;top=114;right=229;bottom=155;z=2};
static={cls="static";text="www.aardio.com";left=93;top=41;right=266;bottom=72;align="center";color=16711680;edge=1;font=LOGFONT(name='Microsoft Sans Serif';underline=1);notify=1;transparent=1;z=1}
)
/*}}*/

winform.button.oncommand = function(id,event){
    winform.button.text = "璇风◢鍊?....."
    winform.button.disabled = true;

    win.ui.waitCursor(true);//榧犳爣鎸囬拡杩涘叆绛夊緟鐘舵�?    win.delay(2000)
    win.ui.waitCursor(false);;//杩樺師榧犳爣鎸囬拡

    winform.button.text = "宸插畬鎴?
    winform.button.disabled = false;
}

import win.cur;

//榧犳爣鍥炲埌绐椾綋涓婃椂,鍒囨崲榧犳爣涓虹澶?winform.wndproc = function(hwnd,message,wParam,lParam){
    if(message =  0x20/*_WM_SETCURSOR*/){
        win.cur.load(0x7F00/*_IDC_ARROW*/)
        win.cur.setCur();
    }
}

//褰撻紶鏍囨寚閽堢Щ鍒伴潤鎬佹帶浠朵笂鏄?鍒囨崲榧犳爣涓烘墜褰?var hand = win.cur.load(32649/*_IDC_HAND*/)
winform.static.wndproc = function(hwnd,message,wParam,lParam){
    if(message = 0x200/*_WM_MOUSEMOVE*/) {
        win.cur.setCur(hand);
    }
}

winform.show(true);
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Effects/cur.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Effects/cur.md')

