[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 娑叉櫠璁℃椂鍣?
```aardio aardio
//娑叉櫠璁℃椂鍣?import fonts.fontAwesome;
import win.ui;
/*DSG{{*/
var winform = win.form(text="娑叉櫠璁℃椂鍣?;left=-20;top=50;right=327;bottom=362;bgcolor=16777215;border="none";max=false)
winform.add(
bk={cls="bk";left=0;top=0;right=349;bottom=27;bgcolor=10789024;z=9};
btnClock={cls="plus";text="鍚姩鏃堕挓";left=68;top=163;right=180;bottom=195;bgcolor=13234329;border={radius=6};notify=1;z=2};
btnColor={cls="plus";text='\uF013';left=287;top=83;right=312;bottom=108;border={radius=6};color=9868950;font=LOGFONT(name='FontAwesome';charset=0);notify=1;z=10};
btnCountDownTimer={cls="plus";text="鍚姩鍊掕鏃?;left=202;top=117;right=314;bottom=149;bgcolor=13234329;border={radius=6};notify=1;z=3};
btnPause={cls="plus";text='\uF04C';left=188;top=214;right=220;bottom=245;border={radius=6};color=2368548;font=LOGFONT(name='FontAwesome';charset=0);notify=1;z=7};
btnStop={cls="plus";text='\uF04D';left=243;top=214;right=275;bottom=245;border={radius=6};color=2368548;font=LOGFONT(name='FontAwesome';charset=0);notify=1;z=8};
btnTimer={cls="plus";text="鍚姩璁℃椂鍣?;left=200;top=163;right=312;bottom=195;bgcolor=13234329;border={radius=6};notify=1;z=4};
datetimepick={cls="datetimepick";left=35;top=121;right=190;bottom=147;edge=1;transparent=1;updown=1;z=5};
lbTip={cls="static";text="鍙屽嚮鏃堕棿鍒囨崲鎮诞鏄剧ず妯″紡";left=35;top=264;right=322;bottom=288;transparent=1;z=6};
plusClock={cls="plus";left=60;top=33;right=279;bottom=93;notify=1;z=1}
)
/*}}*/

var style = {
    icon = {
        background={
            active=0xFF0078B0;
            hover=0xFF00AEFF;
            default=0;
        };
    };
    button = {
        background={
            active=0xFF0078B0;
            hover=0xFF00AEFF;
            disabled=0xFFCCCCCC;
        };
    }
}

winform.btnStop.skin(style.icon)
winform.btnPause.skin(style.icon)
winform.btnCountDownTimer.skin(style.button)
winform.btnClock.skin(style.button)
winform.btnTimer.skin(style.button)

import win.ui.lcdClock;
var lcdClock = win.ui.lcdClock(winform.plusClock);
if(!lcdClock.setImageAttributes) error("璇峰厛鏇存柊 win.ui.lcdClock 鎵╁睍搴?,2)
lcdClock.startClock();

winform.onMinimize = function(lParam){
    winform.plusClock.orphanWindow(true)
    win.setTopmost(winform.plusClock.hwnd)
    winform.modifyStyleEx(0x40000/*_WS_EX_APPWINDOW*/,0x80/*_WS_EX_TOOLWINDOW*/);
    winform.transparent(0)
    winform.plusClock.floating = true;
    return true;
}

winform.plusClock.onMouseDown = function(wParam,lParam){
    if( winform.plusClock.floating ) {
        ::User32.SendMessage(owner.hwnd,0xA1/*_WM_NCLBUTTONDOWN*/,2/*_HTCAPTION*/,0);
    }
    else {
        winform.hitCaption();
    }
}

winform.plusClock.onMouseDoubleClick = function(wParam,lParam){
    if( !winform.plusClock.floating ) {
        winform.hitMin();
        return;
    }

    winform.plusClock.floating = false;

    winform.transparent(false)
    win.setTopmost(winform.plusClock.hwnd,false)
    winform.modifyStyleEx(0x80/*_WS_EX_TOOLWINDOW*/,0x40000/*_WS_EX_APPWINDOW*/);
    winform.resize();
    winform.datetimepick.redraw();
}

winform.btnClock.oncommand = function(id,event){
    lcdClock.startClock()
    winform.btnClock.disabled = true;
    winform.btnCountDownTimer.disabled = false;
    winform.btnTimer.disabled = false;
}

import fsys.media;
winform.btnCountDownTimer.oncommand = function(id,event){
    winform.btnClock.disabled = false;
    winform.btnCountDownTimer.disabled = true;
    winform.btnTimer.disabled = false

    lcdClock.startCountDownTimer(,function(){
        winform.btnCountDownTimer.disabled = false;
        fsys.media.playSound("C:\Windows\media\Ring05.wav")
    })
}

winform.btnTimer.oncommand = function(id,event){
    lcdClock.startTimer();

    winform.btnClock.disabled = false;
    winform.btnCountDownTimer.disabled = false;
    winform.btnTimer.disabled = true;
}

winform.btnPause.oncommand = function(id,event){
    lcdClock.pause();

    winform.btnClock.disabled = false;
    winform.btnCountDownTimer.disabled = false;
    winform.btnTimer.disabled = false;
}

winform.datetimepick.setFormat("' 璁剧疆鍊掕鏃?'HH':'mm':'ss");
winform.datetimepick.time = time.iso8601(0);
winform.datetimepick.onnotify = function(id,code,ptr){
    if(code == 0xFFFFFD09/*_DTN_DATETIMECHANGE*/){
        lcdClock.resetCountDownTimer( winform.datetimepick.time )
        winform.btnClock.disabled = false;
        winform.btnCountDownTimer.disabled = false;
        winform.btnTimer.disabled = false
    }
}

winform.btnStop.oncommand = function(id,event){
    lcdClock.stop();

    winform.btnClock.disabled = false;
    winform.btnCountDownTimer.disabled = false;
    winform.btnTimer.disabled = false;
}

import win.ui.simpleWindow2;
var simpleWindow2 = win.ui.simpleWindow2(winform);

import win.ui.tooltip;
var tooltipCtrl = win.ui.tooltip( winform );//鍦ㄧ獥鍙ｄ笂鍒涘缓tooltip鎺т欢
tooltipCtrl.addTool(winform.btnStop,"鍋滄璁℃椂" )
tooltipCtrl.addTool(winform.btnPause,"鏆傚仠璁℃椂" )
tooltipCtrl.addTool(winform.btnClock,"鏄剧ず鏃堕挓锛屼笉浼氭竻闆惰鏃跺櫒" )
tooltipCtrl.addTool(simpleWindow2.titlebarMin,"鐐硅繖閲岄殣钘忕獥鍙ｅ苟鎮诞鏄剧ず璁℃椂鍣? )
tooltipCtrl.addTool(winform.plusClock,"榧犳爣宸﹂敭鎸変綇鍙互鎷栧姩,鍙屽嚮鍙互鍒囨崲鏄剧ず妯″紡" )

import fsys.config;
var config = fsys.config(io.appData("aardio/std/lcdClock"))
if(config.setting.color){
    lcdClock.setColor(config.setting.color);
}

winform.btnColor.skin({
    background={
        active=0xFF0078B0;
        hover=0xFF00AEFF;
    };
})

import win.ui.ctrl.pick;
winform.btnColor.oncommand = function(id,event){
    var picker = win.ui.ctrl.pick(winform);

    if(config.setting.color){
        picker.setColor(config.setting.color);
    }
    picker.onColorChange = function(argb){
        lcdClock.setColor(argb);
        config.setting.color = argb;
    }

    picker.onInitDialog = function(){
        win.center(picker.hwnd,winform.hwnd);
        picker.top = winform.top + winform.btnColor.bottom;
    }

    picker.doModal()
}

winform.show()
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/aardio/DateTime/clock.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/aardio/DateTime/clock.md')

