[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 下载解压�?
```aardio aardio
//下载解压�?import console;
import ..sevenZip.decoder2.httpFile;

var exDir = ..sevenZip.decoder2.httpFile.download(
    "https://jaist.dl.sourceforge.net/project/mplayerwin/MPlayer-MEncoder/r38151/"
    +  ( _WIN_64 ? "mplayer-svn-38151-x86_64.7z":"mplayer-svn-38151.7z" )
    ,"正在下载 MPlayer 组件",..io.appData("aardio/std/mplayer/"),,"mplayer.7z",winform)

if(exDir){
    console.log(exDir)
}
console.pause()

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/File/7Zip/7zHttpFile.md)

