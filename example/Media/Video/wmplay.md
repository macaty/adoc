[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: mediaplayer 视频播放器控�?
```aardio aardio
import fonts.fontAwesome;
import win.ui;
/*DSG{{*/
var winform = win.form(text="mediaplayer 视频播放器控�?;right=896;bottom=662;bgcolor=16777215)
winform.add(
btnFullScreen={cls="plus";text='\uF047';left=842;top=627;right=883;bottom=657;color=1938422;db=1;dr=1;font=LOGFONT(h=-16;name='FontAwesome');notify=1;repeat="center";z=7};
btnPause={cls="plus";text="暂停";left=416;top=629;right=506;bottom=655;align="left";bgcolor=-5197169;db=1;disabled=1;dl=1;dr=1;font=LOGFONT(h=-16);iconStyle={align="left";font=LOGFONT(h=-16;name='FontAwesome');padding={left=14;top=2}};iconText='\uF04C';notify=1;textPadding={left=35};z=5};
btnPlay={cls="plus";text="播放";left=533;top=629;right=623;bottom=655;align="left";bgcolor=-5197169;db=1;dr=1;font=LOGFONT(h=-16);iconStyle={align="left";font=LOGFONT(h=-16;name='FontAwesome');padding={left=14;top=2}};iconText='\uF04B';notify=1;textPadding={left=35};z=2};
plus2={cls="plus";text='\uF027';left=690;top=632;right=715;bottom=655;color=1938422;db=1;dr=1;font=LOGFONT(h=-19;name='FontAwesome');repeat="scale";z=4};
progress={cls="plus";left=29;top=612;right=879;bottom=616;bgcolor=6447459;db=1;dl=1;dr=1;forecolor=9959653;hide=1;notify=1;z=3};
video={cls="custom";left=30;top=16;right=880;bottom=611;bgcolor=0;db=1;dl=1;dr=1;dt=1;edge=1;z=1};
volume={cls="plus";left=720;top=636;right=836;bottom=648;bgcolor=-2512093;border={radius=-1};color=23807;db=1;dr=1;foreRepeat="expand";foreRight=13;forecolor=-14911489;notify=1;paddingBottom=5;paddingTop=5;z=6}
)
/*}}*/

//创建控件
//https://docs.microsoft.com/zh-cn/windows/win32/wmp/object-model-reference-for-scripting
var wmp = winform.video.createEmbedEx("wmplayer.OCX");

//打开音视频触发此事件
wmp.MediaChange = function(item){
    winform.progress.setProgressRange(0,wmp.currentMedia.duration);
    winform.progress.hide = false;
}

//播放状态变更触发此事件
wmp.PlayStateChange = function(state) {
    if(state==3){
        winform.btnPause.disabled = false;
        winform.btnPlay.checked = true;
    }
    elseif(state<=1){
        winform.btnPause.disabled = true;
        winform.btnPause.checked = false;
        winform.btnPlay.checked = false;
    }
};

//打开视频
wmp.Url  = "http://download.aardio.com/demo/video.aardio";
wmp.stretchToFit = true;
wmp.uiMode = "none";//隐藏默认控制条（不支持高分屏，自己实现一个比较好�?
//暂停按钮事件
winform.btnPause.oncommand = function(id,event){
        if(wmp.playState==3){
        wmp.Controls.pause();
    }
    elseif(wmp.playState==2){
        wmp.Controls.play();
    }
}

//播放按钮事件
winform.btnPlay.oncommand = function(id,event){

    if(!winform.btnPlay.checked){
        if(wmp.playState>1){
            wmp.Controls.stop();
            winform.progress.progressPos = 0;
        }
        return;
    }

    wmp.Controls.play();
}

//使用定时器同步显示视频进�?winform.setInterval(
    function(){
        if(winform.btnPlay.checked && !winform.progress.hide){
            winform.progress.progressPos = wmp.controls.currentPosition;

        }
    },200
);

//显示声音大小
winform.volume.setTrackbarRange(1,100);
winform.volume.progressPos = 100;

//调整声音大小
winform.volume.onPosChanged = function( pos,triggeredByUser ){
    if(triggeredByUser){
        wmp.settings.volume = winform.volume.progressPos;
    }
}

//全屏按钮
winform.btnFullScreen.oncommand = function(id,event){
    wmp.fullScreen = true;
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

winform.btnPause.skin({
    background={
        default=0x668FB2B0;
        disabled=0xFFCCCCCC;
        hover=0xFF928BB3
    };
    color={
        default=0xFF000000;
        disabled=0xFF6D6D6D
    };
    checked = {
        iconText = '\uF04B';
        text = "继续";
        background={
            default=0x668FB2B0;
            disabled=0xFFCCCCCC;
            hover=0xFF928BB3
        };
        color={
            default=0xFF000000;
            disabled=0xFF6D6D6D
        };
    }
})

winform.btnPlay.skin({
    background={
        default=0x668FB2B0;
        disabled=0xFFCCCCCC;
        hover=0xFF928BB3
    };
    color={
        default=0xFF000000;
        disabled=0xFF6D6D6D
    };
    checked = {
        iconText = '\uF04D';
        text = "停止";
        background={
            default=0x668FB2B0;
            disabled=0xFFCCCCCC;
            hover=0xFF928BB3
        };
        color={
            default=0xFF000000;
            disabled=0xFF6D6D6D
        };
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

winform.show(true)
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Media/Video/wmplay.md)

