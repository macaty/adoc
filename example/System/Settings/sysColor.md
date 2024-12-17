[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 绯荤粺绐楀彛鑳屾櫙鑹茶缃伐鍏?
```aardio aardio
//绯荤粺绐楀彛鑳屾櫙鑹?import win.ui;
import win.ui.ctrl.pick;
/*DSG{{*/
var winform = win.form(text="绯荤粺绐楀彛鑳屾櫙鑹茶缃伐鍏?;right=742;bottom=472;bgcolor=16777215;border="thin";composited=1;exmode="toolwindow";max=false;min=false)
winform.add(
chkSaveReg={cls="checkbox";text="鍦ㄦ敞鍐岃〃涓繚瀛樼獥鍙ｈ儗鏅壊璁剧疆锛屼互閬垮厤閲嶅惎鎴栨敞閿�鍚庡け鏁?;left=20;top=9;right=386;bottom=31;bgcolor=16777215;z=2};
colorPick={cls="pick";text="鑷畾涔夋帶浠?;left=17;top=47;right=718;bottom=450;z=1}
)
/*}}*/

//棰滆壊鏀瑰彉鏃惰Е鍙戞浜嬩欢
winform.colorPick.onColorChange = function(clr){

    if( winform.timerSetSysColor ) winform.clearInterval(winform.timerSetSysColor)
    winform.timerSetSysColor = winform.setTimeout(
        function(){
            var r,g,b,a = color.getRgba(clr);
            var rgb = color.rgb(r,g,b);

            if( a != 0xFF) {
                winform.colorPick.setColor(clr,true);
            }

            ::User32.SetSysColors(1,
                { int elements[] = { 0x5/*_COLOR_WINDOW*/ };  } ,
                {INT colors[] = {rgb};}
            );

            if( winform.chkSaveReg.checked ){
                import win.reg;
                var reg = win.reg("HKEY_CURRENT_USER\Control Panel\Colors");
                reg.setSzValue("Window",string.format("%d %d %d",r,g,b));
                reg.close();
            }
        },300)
 }

//鍙�夋寚瀹氬垵濮嬮鑹?winform.colorPick.setColor(  ::User32.GetSysColor(0x5/*_COLOR_WINDOW*/),true );

winform.chkSaveReg.oncommand = function(id,event){
    if( winform.chkSaveReg.checked ){
        import win.reg;
        var reg = win.reg("HKEY_CURRENT_USER\Control Panel\Colors");
        reg.setSzValue("Window",string.format("%d %d %d", winform.colorPick.getRgba() ));
        reg.close();
    }
}

import ide;
win.setOwner(winform.hwnd,ide.getMainHwnd());
winform.onClose = function(hwnd,message,wParam,lParam){
    win.setOwner(winform.hwnd,0)
}

winform.show()
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/System/Settings/sysColor.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/System/Settings/sysColor.md')

