[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鏂偣缁紶

```aardio aardio
//鏂偣缁紶
import fsys;
import inet.httpFile;
import console;

var remoteFile = inet.httpFile(
    "http://wubi.aardio.com/update/wubiLex.7z" ,"/.download/"
    )

var ok,err,errCode = remoteFile.test()
if( ok ){
    return console.logPause("鏂囦欢宸蹭笅杞藉畬鎴愩�佹湇鍔″櫒鏈洿鏂?鏃犻渶閲嶆柊涓嬭浇");
}
elseif( ok === null ){
    return console.logPause("涓嬭浇閿欒,HTTP閿欒浠ｇ爜",remoteFile.statusCode,err);
}

import console.progress;
var progress = console.progress();
remoteFile.onReceiveBegin = function(statusCode,contentLength,fileSize){
    if( statusCode == 206/*鏂偣缁紶*/ ){
        progress.setProgress((fileSize/contentLength)*100,"姝ｅ湪鏂偣缁紶")
    }
    elseif(fileSize){
        progress.setProgress((fileSize/contentLength)*100,"姝ｅ湪閲嶆柊涓嬭浇")
    }
}

remoteFile.onReceive = function(str,downSize,contentLength){
    progress.addProgress((downSize/contentLength)*100
            ,"姝ｅ湪涓嬭浇 鏂囦欢澶у皬锛? + math.size64(contentLength).format() )
}

//涓嬭浇鏂囦欢
var ok,err,fileSize = remoteFile.download()
console.log( ok,err,inet.lastResponse() )
console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Network/Transfer/httpFile.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 服务器报告访问的文件是隐藏的。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Network/Transfer/httpFile.md')

