[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: RAR 瑙ｅ帇

```aardio aardio
//RAR 瑙ｅ帇
import console.int
import console.progress;
var bar = console.progress();

//涓嶉渶瑕佸畨瑁?WinRAR 绛夎蒋浠?涓�鍙ヤ唬鐮佽В鍘?RAR 鏂囦欢
import fsys.unrar;
var ok,errMsg = fsys.unrar.extract("/test.rar",,
    , function(percent,totalSize,unpackSize,filename,rarHeader){
        bar.setProgress(percent,percent +"% 姝ｅ湪瑙ｅ帇锛?+filename);
    }
)

assert(ok,errMsg )

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/File/Compression/unrar.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/File/Compression/unrar.md')

