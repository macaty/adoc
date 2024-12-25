[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: tar.gz 压缩解压

```aardio aardio
//tar.gz 压缩解压

import console;
import fsys.tar;
import fsys.untar;

//tar 打包
var tarFile = fsys.tar("/test.tar.gz");
tarFile.onWriteFile = function( filename ){
        console.log("已打�?,filename)
}
tarFile.pack("~/lib/fsys/")
tarFile.close(); //关闭并释放文�?
//tar 解包
var tar = fsys.untar( "/test.tar.gz","/解压目录" );
for(fileName,writeSize,remainSize in tar.eachBlock() ){
    console.printf("正在解压�?s 字节数：%d",fileName,writeSize  )
}

console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/File/Compression/tar.gz.md)

