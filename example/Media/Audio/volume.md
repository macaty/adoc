[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鑾峰彇銆佽缃郴缁熼煶閲忔紨绀虹▼搴?
```aardio aardio
//闊抽噺璋冭妭
import fonts.fontAwesome;
import win.ui;
/*DSG{{*/
var winform = win.form(text="鑾峰彇銆佽缃郴缁熼煶閲忔紨绀虹▼搴?;right=711;bottom=199;border="dialog frame";max=false)
winform.add(
btnVolumeDown={cls="button";text='\uF028 鍑忓皯闊抽噺';left=288;top=128;right=430;bottom=160;font=LOGFONT(name='FontAwesome');z=5};
btnVolumeMute={cls="button";text='\uF026 鍒囨崲闈欓煶';left=472;top=128;right=614;bottom=160;font=LOGFONT(name='FontAwesome');z=6};
btnVolumeUp={cls="button";text='\uF028 澧炲姞闊抽噺';left=112;top=128;right=254;bottom=160;font=LOGFONT(name='FontAwesome');z=4};
lbWmplayer={cls="static";left=16;top=16;right=683;bottom=60;dl=1;dr=1;dt=1;notify=1;z=1};
static2={cls="static";text="鎷栧姩鍙充晶婊戝潡璋冩暣绯荤粺闊抽噺锛?;left=8;top=80;right=216;bottom=104;align="right";db=1;dl=1;transparent=1;z=3};
trackbar={cls="trackbar";left=224;top=72;right=680;bottom=102;db=1;dl=1;dr=1;max=100;min=0;z=2}
)
/*}}*/

//鍒涘缓鎾斁鍣ㄦ帶浠?var wmp = winform.lbWmplayer.createEmbed( "WMPlayer.OCX" )._object;
wmp.url = "http://download.aardio.com/v10.files/demo/mp3/lrc.mp3";

import sys.audioVolume;
var volumeCtrl = sys.audioVolume();
winform.trackbar.setRange(0,100);
winform.trackbar.pos = volumeCtrl.volume;

//浣跨敤volumeCtrl.volume鍙互鏇存柟渚跨殑鐩存帴璋冩暣闊抽噺
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

//涓嬮潰鎻愪緵鍙﹀涓�绉嶈皟鏁撮煶閲忕殑鏂规硶
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

//鍚屾绯荤粺闊抽噺(涓�鑸病鏈夎繖涓繀瑕?
winform.setInterval(
    function(){
        winform.trackbar.pos = !volumeCtrl.mute ? volumeCtrl.volume : 0;
    },500
)

winform.show(true)
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Media/Audio/volume.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Media/Audio/volume.md')

