[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 替换文本

```aardio aardio
//替换文本
import console;
import fsys.batch;

//创建批量处理文件对象，参�?@1 指定目标目录，参�?@2 指定要处理的文件名通配符�?var batch = fsys.batch("~/tools","*.aardio")

//批量处理文件
batch.enumText(
    /*
    枚举指定的文件�?    文件内容读取�?utf8Text，utf8Text �?UTF-8 编码�?    codepage 为文件的源编码�?    fullpath 为文件路径�?    */
    function(utf8Text,codepage,fullpath){
        var utf8Text,count = string.replace(utf8Text,"\.aardio\.aardio",".aardio");
        if(count) return utf8Text,"UTF-8-NOBOM";
    },"\.aardio$"
)

console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/File/Batch/batch.md)

