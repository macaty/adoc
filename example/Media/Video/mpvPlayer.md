[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 MPV 视频播放�?
```aardio aardio
import fonts.fontAwesome;
import win.ui;
/*DSG{{*/
var winform = win.form(text="调用 MPV 视频播放�?;right=856;bottom=483;bgcolor=16515070;)
winform.add(
btnFullScreen={cls="plus";text='\uF047';left=811;top=452;right=852;bottom=482;color=1938422;db=1;dr=1;font=LOGFONT(h=-16;name='FontAwesome');notify=1;repeat="center";z=4};
btnPlay={cls="plus";text='\uF04B';left=10;top=456;right=42;bottom=479;color=1938422;db=1;dl=1;font=LOGFONT(h=-19;name='FontAwesome');notify=1;repeat="scale";z=5};
btnSubtitles={cls="plus";text='\uF03A';left=639;top=455;right=664;bottom=478;color=1938422;db=1;dr=1;font=LOGFONT(h=-19;name='FontAwesome');repeat="scale";z=8};
lbTime={cls="plus";text="00:00:00";left=579;top=455;right=632;bottom=475;db=1;dr=1;z=7};
plus={cls="plus";text='\uF027';left=666;top=454;right=691;bottom=477;color=1938422;db=1;dr=1;font=LOGFONT(h=-19;name='FontAwesome');repeat="scale";z=2};
trackbar={cls="plus";left=49;top=460;right=576;bottom=472;bgcolor=-2512093;border={radius=-1};color=23807;db=1;dl=1;dr=1;foreRepeat="expand";foreRight=13;forecolor=-14911489;notify=1;paddingBottom=5;paddingTop=5;z=1};
video={cls="custom";left=8;top=6;right=848;bottom=447;bgcolor=0;db=1;dl=1;dr=1;dt=1;z=6};
volume={cls="plus";left=696;top=460;right=812;bottom=472;bgcolor=-2512093;border={radius=-1};color=23807;db=1;dr=1;foreRepeat="expand";foreRight=13;forecolor=-14911489;notify=1;paddingBottom=5;paddingTop=5;z=3}
)
/*}}*/

import mpvPlayer;
var mplayer = mpvPlayer(winform.video );

//在视频上写字，所有配置参数文档：http://mpv.io/manual/master/#options
mplayer.setOption("osd-msg1","MPV播放器是极好�?);

//订阅播放进度属性变更事件，所有属性参考文�?http://mpv.io/manual/master/#properties
mplayer.observeProperty("time-pos");//播放进度
mplayer.observeProperty("duration");//视频长度
mplayer.observeProperty("track-list");//加载字幕

//属性变更后触发此事�?mplayer.onPropertyChange = function(name,value){
    if( name == "time-pos" ){
        if( !winform.trackbar.state.active ){
            if(value) winform.trackbar.progressPos = value;
        }
    }
    elseif(name == "duration"){
        if(value) {
            winform.trackbar.setTrackbarRange(1,value);
            winform.btnPlay.disabledText = null;
        }
    }
    elseif(name == "track-list"){
        //winform.cbSubtitles.trackList();//获取视频加载的字�?    }
}

//获取反馈信息
mplayer.requestLogMessages("info");
mplayer.onLogMessage = function(text,prefix,level,levelId){

}

//文件播放结束触发此事�?mplayer.onEndFile = function(reason,err){
    winform.btnPlay.checked = false;
}

//启动一个定时器用于分发播放器事件（不然不会触发任何事件�?var tmId = winform.setInterval(
    function(){
        event = mplayer.waitEvent(0);
        if( event.id == 8/*_MPV_EVENT_FILE_LOADED*/){
            //winform.cbSubtitles.trackList();//获取视频加载的字�?            winform.text = mplayer.getMediaTitle();
            winform.btnPlay.disabledText = null;
        }
    },10
)

import fsys.dlg;
winform.btnPlay.oncommand = function(id,event){

    if( winform.btnPlay.checked ){

        if(!mplayer.filename() ){
            mplayer.loadFile("http://download.aardio.com/demo/video.aardio");
            winform.btnPlay.disabledText = {'\uF254';'\uF251';'\uF252';'\uF253';'\uF250'}
        }

        mplayer.play();
    }
    else {
        mplayer.stop();
        winform.trackbar.progressPos = 0;
    }
}

import win.debounce;
var seekDebounce = win.debounce( function(pos){
    mplayer.seek( pos  )
},50)

winform.trackbar.onPosChanged = function( pos,triggeredByUser ){
    if(triggeredByUser){
        seekDebounce(pos);
    }

    winform.lbTime.text = time(pos,"!%H:%M:%S");
}

import win.ui.menu;
winform.btnSubtitles.oncommand = function( id,event ){

    var subCount = 0;
    var count = mplayer.getTrackCount();

    var menu = win.ui.popmenu(winform);
    for(i=1;count){
        if( mplayer.getTrackType(i) == "sub" ){
            subCount ++;
            var id = menu.add(mplayer.getTrackTitle(i),function(){
                mplayer.setSubtitle( mplayer.getTrackId(i) );
            })
            menu.check(id,mplayer.getTrackSelected(i),0);
        }
    }

    if(!subCount){
        return winform.msgboxErr("无字�?)
    }

    menu.popup();
}

winform.volume.setTrackbarRange(1,100)
winform.volume.progressPos = mplayer.getVolume();
winform.volume.onPosChanged = function( pos,triggeredByUser ){
    if(triggeredByUser){
        mplayer.setVolume(winform.volume.progressPos)
    }
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

winform.trackbar.setTrackbarRange(1,100);
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

winform.btnSubtitles.skin({
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
        text = '\uF04D'
    }
})

winform.btnFullScreen.oncommand = function(id,event){
    winform.video.fullscreen();
}

winform.show()
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Media/Video/mpvPlayer.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Media/Video/mpvPlayer.md')

