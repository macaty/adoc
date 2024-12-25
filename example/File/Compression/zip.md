[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: zip 压缩

```aardio aardio
//zip 压缩
import console;
import zlib.zip

var zip = zlib.zip("/测试文件.zip");
zip.compress( io._exedir + "config",
    function(len,path){
        console.log( len,path )
    }
)

raw.explore("/测试文件.zip","/select");

/*
import System.IO.Compression.ZipFile;
var ZipFile = System.IO.Compression.ZipFile;

//简单压缩目录也可以调用 Win10 及更新系统自带组�?ZipFile.CreateFromDirectory (
    io.fullpath("/测试文件/"),
    io.fullpath("/测试文件.zip"),
    0,false )
*/

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/File/Compression/zip.md)

