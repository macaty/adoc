[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 涓嬭浇瑙ｅ帇缂?
```aardio aardio
//涓嬭浇瑙ｅ帇缂?import console;
import ..sevenZip.decoder2.httpFile;

var exDir = ..sevenZip.decoder2.httpFile.download(
    "https://jaist.dl.sourceforge.net/project/mplayerwin/MPlayer-MEncoder/r38151/"
    +  ( _WIN_64 ? "mplayer-svn-38151-x86_64.7z":"mplayer-svn-38151.7z" )
    ,"姝ｅ湪涓嬭浇 MPlayer 缁勪欢",..io.appData("aardio/std/mplayer/"),,"mplayer.7z",winform)

if(exDir){
    console.log(exDir)
}
console.pause()

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/File/7Zip/7zHttpFile.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/File/7Zip/7zHttpFile.md')

