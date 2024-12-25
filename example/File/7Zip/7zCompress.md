[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 压缩

```aardio aardio
//压缩
import console;
import sevenZip.cmd;

console.open()
sevenZip.cmd.compress( "~/tools"
    ,"\test.7z"
    ,console.log //这里可以设置一个回调函�?输出回显结果
    )
io.print("压缩完成")

sevenZip.cmd.extract( "\test.7z"
    ,"\test"
    ,console.log //这里可以设置一个回调函�?输出回显结果
)
io.print("解压完成")

console.pause();
console.close();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/File/7Zip/7zCompress.md)

