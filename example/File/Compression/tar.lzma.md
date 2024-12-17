[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: tar.lzma 鎵撳寘鍘嬬缉

```aardio aardio
//tar.lzma 鎵撳寘鍘嬬缉
import console;
import fsys.dlg.dir;
import fsys.tar;

var fullpath = fsys.dlg.dir(,,'璇烽�夋嫨瑕佹墦鍖呯殑鐩綍')
if(!fullpath) return;

//tar鎵撳寘
var tarPath = fsys.path.removeBackslash(fullpath) + ".tar"
var tarFile = fsys.tar(tarPath);
tarFile.onWriteFile = function( filename ){
    console.log("宸叉墦鍖?,filename)
}
tarFile.pack(fullpath);
tarFile.close();

//鍘嬬缉涓?tar.lzma 鏍煎紡
import sevenZip.lzma;
console.log("姝ｅ湪鍘嬬缉涓簂zma鏂囦欢")
sevenZip.lzma.encodeFile(tarPath,tarPath + ".lzma");
console.log("鎵撳寘瀹屾垚")
console.pause();

import fsys.dlg.dir;

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/File/Compression/tar.lzma.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/File/Compression/tar.lzma.md')

