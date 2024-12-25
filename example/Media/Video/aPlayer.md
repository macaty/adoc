[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: aPlayer

```aardio aardio
import win.ui;
/*DSG{{*/
var winform = win.form(cls="aplayerform";text="调用 aplayer 视频播放器控�?;right=835;bottom=484)
winform.add()
/*}}*/

import thunder.aPlayer;
var aPlayer = thunder.aPlayer(winform)

//播放器事�?aPlayer.OnMessage = function(message,wParam,lParam){

}

//按需下载解码�?aPlayer.OnDownloadCodec =  function(strCodecPath){
    if( ! winform.msgboxTest("当前视频缺少必须的解码器文件，是否现在下载？","aPlayer播放�?) )
            return;

    import zlib.httpFile;
    zlib.httpFile.download("http://aplayer.open.xunlei.com/codecs.zip","正在下载解码�?,"/download","~\lib\thunder\aPlayer\.res\codecs",,winform)
    aPlayer.setConfig( 19 ); //通知解码器下载完�?默认为解码器异步下载模式,可以先退出OnDownloadCodec事件再下载解码器)
}

aPlayer.open("http://download.aardio.com/demo/video.aardio");
aPlayer.play()

//全屏
//winform.fullscreen(true);
winform.show()
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Media/Video/aPlayer.md)

