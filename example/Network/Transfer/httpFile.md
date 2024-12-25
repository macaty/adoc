[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 断点续传

```aardio aardio
//断点续传
import fsys;
import inet.httpFile;
import console;

var remoteFile = inet.httpFile(
    "http://wubi.aardio.com/update/wubiLex.7z" ,"/.download/"
    )

var ok,err,errCode = remoteFile.test()
if( ok ){
    return console.logPause("文件已下载完成、服务器未更�?无需重新下载");
}
elseif( ok === null ){
    return console.logPause("下载错误,HTTP错误代码",remoteFile.statusCode,err);
}

import console.progress;
var progress = console.progress();
remoteFile.onReceiveBegin = function(statusCode,contentLength,fileSize){
    if( statusCode == 206/*断点续传*/ ){
        progress.setProgress((fileSize/contentLength)*100,"正在断点续传")
    }
    elseif(fileSize){
        progress.setProgress((fileSize/contentLength)*100,"正在重新下载")
    }
}

remoteFile.onReceive = function(str,downSize,contentLength){
    progress.addProgress((downSize/contentLength)*100
            ,"正在下载 文件大小�? + math.size64(contentLength).format() )
}

//下载文件
var ok,err,fileSize = remoteFile.download()
console.log( ok,err,inet.lastResponse() )
console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Network/Transfer/httpFile.md)

