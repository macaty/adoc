[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 MPlayer 视频播放器（按回车全屏，按空格暂停）

```aardio aardio
import fonts.fontAwesome;
import win.ui;
/*DSG{{*/
var winform = win.form(text="调用 MPlayer 视频播放器（按回车全屏，按空格暂停）";right=856;bottom=483;bgcolor=16515070)
winform.add(
btnFullScreen={cls="plus";text='\uF047';left=811;top=453;right=852;bottom=483;color=1938422;db=1;dr=1;font=LOGFONT(h=-16;name='FontAwesome');iconStyle={align="left";font=LOGFONT(h=-13;name='FontAwesome');padding={left=8}};notify=1;repeat="center";z=4};
btnPlay={cls="plus";text='\uF04B';left=10;top=456;right=42;bottom=479;color=1938422;db=1;dl=1;font=LOGFONT(h=-19;name='FontAwesome');notify=1;repeat="scale";z=5};
plus={cls="plus";text='\uF027';left=666;top=457;right=691;bottom=480;color=1938422;db=1;dr=1;font=LOGFONT(h=-19;name='FontAwesome');repeat="scale";z=2};
trackbar={cls="plus";left=49;top=460;right=652;bottom=472;bgcolor=-2512093;border={radius=-1};color=23807;db=1;dl=1;dr=1;foreRepeat="expand";foreRight=13;forecolor=-14911489;notify=1;paddingBottom=5;paddingTop=5;z=1};
video={cls="custom";left=8;top=6;right=848;bottom=447;bgcolor=0;db=1;dl=1;dr=1;dt=1;z=6};
volume={cls="plus";left=696;top=461;right=812;bottom=473;bgcolor=-2512093;border={radius=-1};color=23807;db=1;dr=1;foreRepeat="expand";foreRight=13;forecolor=-14911489;notify=1;paddingBottom=5;paddingTop=5;z=3}
)
/*}}*/

import process.mplayer;
var mplayer = process.mplayer( , winform.video );

import fsys.dlg;
winform.btnPlay.oncommand = function(id,event){
    if(!mplayer.isPlaying()){
        if(mplayer.isPaused()){
            mplayer.pause();
        }
        elseif( mplayer.loadfile( fsys.dlg.open(,"请指定视频文�?) ) ){
            var length = mplayer.getTimeLength();
            if(length)winform.trackbar.setTrackbarRange(1,length);
        }
        else {
            winform.btnPlay.checked = false;
        }
    }
    else {
        mplayer.pause();
    }
}

winform.trackbar.onMouseUp = function(){
    mplayer.seekSecond(winform.trackbar.progressPos);
}

winform.volume.setTrackbarRange(1,100);
winform.volume.progressPos = 100;
winform.volume.onMouseUp = function(){
    mplayer.volume(winform.volume.progressPos,true)
}

winform.trackbar.setTrackbarRange(1,100);
winform.setInterval(
    function(){
        var pos = mplayer.getTimePos();
        if(pos) winform.trackbar.progressPos = pos;
    },1000
)

winform.btnFullScreen.oncommand = function(id,event){
    winform.video.fullscreen(true);
}

//按空格暂�?winform.translateAccelerator = function(msg){
    if(  msg.wParam == 0x20/*_VK_SPACE*/ && msg.message = 0x101/*_WM_KEYUP*/){
        return true;
    }
}

//按回车全�?winform.onOk = function(){
    winform.video.fullscreen();
}

//按回车全�?winform.video.onOk = function(){
    winform.video.fullscreen();
}

//�?ESC 退出全�?winform.video.onCancel = function(){
    winform.video.fullscreen(false);
}

winform.volume.skin({
    background={
        default=0xFF23ABD9
    };
    foreground={
        default=0xFFFF771C;
        hover=0xFFFF6600
    };
    color={
        default=0xFFFF5C00;
        hover=0xFFFF6600
    }
})

winform.trackbar.skin({
    background={
        default=0xFF23ABD9
    };
    foreground={
        default=0xFFFF771C;
        hover=0xFFFF6600
    };
    color={
        default=0xFFFF5C00;
        hover=0xFFFF6600
    }
})

winform.btnFullScreen.skin({
    color={
        active=0xFF00FF00;
        default=0xFFF6931D;
        disabled=0xFF6D6D6D;
        hover=0xFFFF0000
    }
})

winform.btnPlay.skin({
    color={
        active=0xFF00FF00;
        default=0xFFF6931D;
        disabled=0xFF6D6D6D;
        hover=0xFFFF0000
    }
    checked={
        text = '\uF04C'
    }
})

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Media/Video/mplayer.md)

