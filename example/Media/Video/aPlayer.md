[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: aPlayer

```aardio aardio
import win.ui;
/*DSG{{*/
var winform = win.form(cls="aplayerform";text="璋冪敤 aplayer 瑙嗛鎾斁鍣ㄦ帶浠?;right=835;bottom=484)
winform.add()
/*}}*/

import thunder.aPlayer;
var aPlayer = thunder.aPlayer(winform)

//鎾斁鍣ㄤ簨浠?aPlayer.OnMessage = function(message,wParam,lParam){

}

//鎸夐渶涓嬭浇瑙ｇ爜鍣?aPlayer.OnDownloadCodec =  function(strCodecPath){
    if( ! winform.msgboxTest("褰撳墠瑙嗛缂哄皯蹇呴』鐨勮В鐮佸櫒鏂囦欢锛屾槸鍚︾幇鍦ㄤ笅杞斤紵","aPlayer鎾斁鍣?) )
            return;

    import zlib.httpFile;
    zlib.httpFile.download("http://aplayer.open.xunlei.com/codecs.zip","姝ｅ湪涓嬭浇瑙ｇ爜鍣?,"/download","~\lib\thunder\aPlayer\.res\codecs",,winform)
    aPlayer.setConfig( 19 ); //閫氱煡瑙ｇ爜鍣ㄤ笅杞藉畬鎴?榛樿涓鸿В鐮佸櫒寮傛涓嬭浇妯″紡,鍙互鍏堥��鍑篛nDownloadCodec浜嬩欢鍐嶄笅杞借В鐮佸櫒)
}

aPlayer.open("http://download.aardio.com/demo/video.aardio");
aPlayer.play()

//鍏ㄥ睆
//winform.fullscreen(true);
winform.show()
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Media/Video/aPlayer.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Media/Video/aPlayer.md')

