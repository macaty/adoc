[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: tar.lzma 打包压缩

```aardio aardio
//tar.lzma 打包压缩
import console;
import fsys.dlg.dir;
import fsys.tar;

var fullpath = fsys.dlg.dir(,,'请选择要打包的目录')
if(!fullpath) return;

//tar打包
var tarPath = fsys.path.removeBackslash(fullpath) + ".tar"
var tarFile = fsys.tar(tarPath);
tarFile.onWriteFile = function( filename ){
    console.log("已打�?,filename)
}
tarFile.pack(fullpath);
tarFile.close();

//压缩�?tar.lzma 格式
import sevenZip.lzma;
console.log("正在压缩为lzma文件")
sevenZip.lzma.encodeFile(tarPath,tarPath + ".lzma");
console.log("打包完成")
console.pause();

import fsys.dlg.dir;

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/File/Compression/tar.lzma.md)

