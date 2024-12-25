[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: zip 解压

```aardio aardio
//zip 解压
import console;
import fsys.dlg;
import zlib.unzip;

var ok,err = zlib.unzip.extract( fsys.dlg.open("*.zip|*.zip","请选择需要解压的zip文件"),"/my",
    function(fileName,extractPath,fileInfo,size,unitSize,unitName){
        if( size !== null )
            console.log( "正在解压文件",fileName,size++ unitName );
        else {
            console.log( "正在解压目录",fileName );
        }

        return true;
    }
)

console.pause();

/*
import System.IO.Compression.ZipFile;
var ZipFile = System.IO.Compression.ZipFile;

//简单解压缩也可以调�?Win10 及更新系统自带组�?ZipFile.ExtractToDirectory (
    io.fullpath("/测试文件.zip"),
    io.fullpath("/测试文件/")
    )
*/

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/File/Compression/unzip.md)

