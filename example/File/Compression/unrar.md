[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: RAR 解压

```aardio aardio
//RAR 解压
import console.int
import console.progress;
var bar = console.progress();

//不需要安�?WinRAR 等软�?一句代码解�?RAR 文件
import fsys.unrar;
var ok,errMsg = fsys.unrar.extract("/test.rar",,
    , function(percent,totalSize,unpackSize,filename,rarHeader){
        bar.setProgress(percent,percent +"% 正在解压�?+filename);
    }
)

assert(ok,errMsg )

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/File/Compression/unrar.md)

