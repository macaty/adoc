[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 获取、设置系统音量演示程�?
```aardio aardio
//音量调节
import fonts.fontAwesome;
import win.ui;
/*DSG{{*/
var winform = win.form(text="获取、设置系统音量演示程�?;right=711;bottom=199;border="dialog frame";max=false)
winform.add(
btnVolumeDown={cls="button";text='\uF028 减少音量';left=288;top=128;right=430;bottom=160;font=LOGFONT(name='FontAwesome');z=5};
btnVolumeMute={cls="button";text='\uF026 切换静音';left=472;top=128;right=614;bottom=160;font=LOGFONT(name='FontAwesome');z=6};
btnVolumeUp={cls="button";text='\uF028 增加音量';left=112;top=128;right=254;bottom=160;font=LOGFONT(name='FontAwesome');z=4};
lbWmplayer={cls="static";left=16;top=16;right=683;bottom=60;dl=1;dr=1;dt=1;notify=1;z=1};
static2={cls="static";text="拖动右侧滑块调整系统音量�?;left=8;top=80;right=216;bottom=104;align="right";db=1;dl=1;transparent=1;z=3};
trackbar={cls="trackbar";left=224;top=72;right=680;bottom=102;db=1;dl=1;dr=1;max=100;min=0;z=2}
)
/*}}*/

//创建播放器控�?var wmp = winform.lbWmplayer.createEmbed( "WMPlayer.OCX" )._object;
wmp.url = "http://download.aardio.com/v10.files/demo/mp3/lrc.mp3";

import sys.audioVolume;
var volumeCtrl = sys.audioVolume();
winform.trackbar.setRange(0,100);
winform.trackbar.pos = volumeCtrl.volume;

//使用volumeCtrl.volume可以更方便的直接调整音量
winform.trackbar.oncommand = function(id,event,pos){
    if( event == 8/*_SB_ENDSCROLL*/ ){
        volumeCtrl.volume = winform.trackbar.pos;
        volumeCtrl.mute = false;
    }
    elseif( event == 5/*_SB_THUMBTRACK*/) {
        volumeCtrl.volume = pos;
        volumeCtrl.mute = false;
    }
}

//下面提供另外一种调整音量的方法
_APPCOMMAND_VOLUME_UP = 10
_APPCOMMAND_VOLUME_DOWN = 9
_APPCOMMAND_VOLUME_MUTE = 8
winform.btnVolumeMute.oncommand = function(id,event){
    ::User32.SendMessage(winform.hwnd,0x319/*_WM_APPCOMMAND*/,0x200eb0, _APPCOMMAND_VOLUME_MUTE  * 0x10000);
}

winform.btnVolumeUp.oncommand = function(id,event){
    ::User32.SendMessage(winform.hwnd,0x319/*_WM_APPCOMMAND*/,0x30292, _APPCOMMAND_VOLUME_UP * 0x10000);
}

winform.btnVolumeDown.oncommand = function(id,event){
    ::User32.SendMessage(winform.hwnd,0x319/*_WM_APPCOMMAND*/,0x30292, _APPCOMMAND_VOLUME_DOWN * 0x10000);

}

//同步系统音量(一般没有这个必�?
winform.setInterval(
    function(){
        winform.trackbar.pos = !volumeCtrl.mute ? volumeCtrl.volume : 0;
    },500
)

winform.show(true)
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Media/Audio/volume.md)

