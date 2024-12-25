[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 已知文件�?
```aardio aardio
//已知文件�?import console;
import fsys.knownFolder;

/*
有部分目录用 io.getSpecial() 无法获取�?例如系统下载目录，这些目录可以用下面�?fsys.knownFolder 获取�?参数@1 指定目录 GUID，GUID 可以�?16 字节的字符串，也可以�?win.guid 支持的格式�?*/
var path = fsys.knownFolder("374DE290-123F-4565-9164-39C4925E467B");

console.log("系统下载目录�?,path );
console.pause(true);

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/File/SpecialPath/knownFolder.md)

