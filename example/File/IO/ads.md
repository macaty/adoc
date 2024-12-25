[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 备用数据�?
```aardio aardio
//备用数据�?import console;
import sys.volume;

if(sys.volume.getInfo("/ads.aardio").fsys!="NTFS"){
    console.logPause("当前分区不是 NTFS 文件系统，不支持命名数据流�?);
    return;
}

//自文件备用数据流读取备用数据
var count = string.load("/ads.aardio:count")
count = (  count : 0 ) + 1;

//写入看不见的备用数据�?也可以叫命名数据�?
string.save("/ads.aardio:count", count);

//显示结果
console.log( "你已经运行了这个代码" +count+ "�? );

import fsys.streamInfo;
var streamInfo = fsys.streamInfo("/ads.aardio")

//显示文件的全部数据流名称
console.dumpJson(streamInfo);
console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/File/IO/ads.md)

