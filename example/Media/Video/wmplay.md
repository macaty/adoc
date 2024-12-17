[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: mediaplayer 瑙嗛鎾斁鍣ㄦ帶浠?
```aardio aardio
import fonts.fontAwesome;
import win.ui;
/*DSG{{*/
var winform = win.form(text="mediaplayer 瑙嗛鎾斁鍣ㄦ帶浠?;right=896;bottom=662;bgcolor=16777215)
winform.add(
btnFullScreen={cls="plus";text='\uF047';left=842;top=627;right=883;bottom=657;color=1938422;db=1;dr=1;font=LOGFONT(h=-16;name='FontAwesome');notify=1;repeat="center";z=7};
btnPause={cls="plus";text="鏆傚仠";left=416;top=629;right=506;bottom=655;align="left";bgcolor=-5197169;db=1;disabled=1;dl=1;dr=1;font=LOGFONT(h=-16);iconStyle={align="left";font=LOGFONT(h=-16;name='FontAwesome');padding={left=14;top=2}};iconText='\uF04C';notify=1;textPadding={left=35};z=5};
btnPlay={cls="plus";text="鎾斁";left=533;top=629;right=623;bottom=655;align="left";bgcolor=-5197169;db=1;dr=1;font=LOGFONT(h=-16);iconStyle={align="left";font=LOGFONT(h=-16;name='FontAwesome');padding={left=14;top=2}};iconText='\uF04B';notify=1;textPadding={left=35};z=2};
plus2={cls="plus";text='\uF027';left=690;top=632;right=715;bottom=655;color=1938422;db=1;dr=1;font=LOGFONT(h=-19;name='FontAwesome');repeat="scale";z=4};
progress={cls="plus";left=29;top=612;right=879;bottom=616;bgcolor=6447459;db=1;dl=1;dr=1;forecolor=9959653;hide=1;notify=1;z=3};
video={cls="custom";left=30;top=16;right=880;bottom=611;bgcolor=0;db=1;dl=1;dr=1;dt=1;edge=1;z=1};
volume={cls="plus";left=720;top=636;right=836;bottom=648;bgcolor=-2512093;border={radius=-1};color=23807;db=1;dr=1;foreRepeat="expand";foreRight=13;forecolor=-14911489;notify=1;paddingBottom=5;paddingTop=5;z=6}
)
/*}}*/

//鍒涘缓鎺т欢
//https://docs.microsoft.com/zh-cn/windows/win32/wmp/object-model-reference-for-scripting
var wmp = winform.video.createEmbedEx("wmplayer.OCX");

//鎵撳紑闊宠棰戣Е鍙戞浜嬩欢
wmp.MediaChange = function(item){
    winform.progress.setProgressRange(0,wmp.currentMedia.duration);
    winform.progress.hide = false;
}

//鎾斁鐘舵�佸彉鏇磋Е鍙戞浜嬩欢
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

//鎵撳紑瑙嗛
wmp.Url  = "http://download.aardio.com/demo/video.aardio";
wmp.stretchToFit = true;
wmp.uiMode = "none";//闅愯棌榛樿鎺у埗鏉★紙涓嶆敮鎸侀珮鍒嗗睆锛岃嚜宸卞疄鐜颁竴涓瘮杈冨ソ锛?
//鏆傚仠鎸夐挳浜嬩欢
winform.btnPause.oncommand = function(id,event){
        if(wmp.playState==3){
        wmp.Controls.pause();
    }
    elseif(wmp.playState==2){
        wmp.Controls.play();
    }
}

//鎾斁鎸夐挳浜嬩欢
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

//浣跨敤瀹氭椂鍣ㄥ悓姝ユ樉绀鸿棰戣繘搴?winform.setInterval(
    function(){
        if(winform.btnPlay.checked && !winform.progress.hide){
            winform.progress.progressPos = wmp.controls.currentPosition;

        }
    },200
);

//鏄剧ず澹伴煶澶у皬
winform.volume.setTrackbarRange(1,100);
winform.volume.progressPos = 100;

//璋冩暣澹伴煶澶у皬
winform.volume.onPosChanged = function( pos,triggeredByUser ){
    if(triggeredByUser){
        wmp.settings.volume = winform.volume.progressPos;
    }
}

//鍏ㄥ睆鎸夐挳
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
        text = "缁х画";
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
        text = "鍋滄";
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

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Media/Video/wmplay.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Media/Video/wmplay.md')

