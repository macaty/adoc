[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: zip 鍘嬬缉

```aardio aardio
//zip 鍘嬬缉
import console;
import zlib.zip

var zip = zlib.zip("/娴嬭瘯鏂囦欢.zip");
zip.compress( io._exedir + "config",
    function(len,path){
        console.log( len,path )
    }
)

raw.explore("/娴嬭瘯鏂囦欢.zip","/select");

/*
import System.IO.Compression.ZipFile;
var ZipFile = System.IO.Compression.ZipFile;

//绠�鍗曞帇缂╃洰褰曚篃鍙互璋冪敤 Win10 鍙婃洿鏂扮郴缁熻嚜甯︾粍浠?ZipFile.CreateFromDirectory (
    io.fullpath("/娴嬭瘯鏂囦欢/"),
    io.fullpath("/娴嬭瘯鏂囦欢.zip"),
    0,false )
*/

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/File/Compression/zip.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/File/Compression/zip.md')

