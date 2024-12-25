[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 播放声音

```aardio aardio
//播放声音
import fsys.dlg;
import win.ui;
/*DSG{{*/
var winform = win.form(text="播放声音";right=506;bottom=186;border="dialog frame";max=false;min=false)
winform.add(
btnActiveMovie={cls="button";text="ActiveMovie 播放声音";left=273;top=74;right=482;bottom=106;z=5};
btnMessageBeep={cls="button";text="系统警报�?;left=29;top=130;right=171;bottom=162;z=2};
btnMp3={cls="button";text="播放 MP3";left=29;top=19;right=171;bottom=51;z=4};
btnWav={cls="button";text="播放 WAV 文件";left=188;top=19;right=330;bottom=51;z=3};
btnWmpOcx={cls="button";text="WMPlayer.OCX 播放网络 MP3";left=29;top=74;right=260;bottom=106;z=1}
)
/*}}*/

import fsys.media;
winform.btnWav.oncommand = function(id,event){

    var path = fsys.dlg.open("*.wav|*.wav||");
    if(!path) return;

    import fsys.media;
    fsys.media.playSound(path);
}

import fsys.media;
winform.btnMp3.oncommand = function(id,event){

    var path = fsys.dlg.open("*.mp3|*.mp3||");
    if(!path) return;

    if(mediaFile) {
        mediaFile.stop();
    }

    mediaFile = fsys.media(path);
    if(mediaFile) {
        mediaFile.play();
    }
}

winform.btnWmpOcx.oncommand = function(id,event){

    /*
    参考：https://docs.microsoft.com/zh-cn/windows/win32/wmp/object-model-reference-for-scripting
    WMPlayer.OCX 只能用于界面线程，可�?:= 操作符避免重复创建对象�?    */
    ..wmPlayer := com.CreateObject("WMPlayer.OCX");

    //使用 COM 对象打开指定的音�?    ..wmPlayer.url = "http://download.aardio.com/v10.files/demo/mp3/lrc.mp3"
}

winform.btnActiveMovie.oncommand = function(id,event){

    var path = fsys.dlg.open("*.mp3|*.mp3||");
    if(!path) return;

    //参考接口定义："\lib\vc6\.vc\Include\IAMOVIE.IDL"
    var axMovie = com.CreateObject("AMOVIE.ActiveMovieControl")
    axMovie.FileName = path;
}

winform.btnMessageBeep.oncommand = function(id,event){
    ::User32.MessageBeep(0x10/*_MB_ICONHAND*/);//播放系统警报�?不是所有电脑都支持
    ::Kernel32.Beep(550,500);//主板发声,不是所有电脑都支持
}

winform.show()
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Media/Audio/audio.md)

