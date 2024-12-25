[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 倒读文件

```aardio aardio
//倒读文件
import console;

//打开文件 https://www.aardio.com/zh-cn/doc/library-guide/builtin/io/file.html
file = io.file("~\Config\intellisense\kernel.txt","r+");

//移动文件指针到尾�?file.seek("end")

//读取最后一�?console.log( file.readback() )

//读取倒数第二�?console.log( file.readback() )

//读取倒数第三�?console.log( file.readback() )

//再向前读�?2个字�?console.log( file.readback(12) )

//向前读取到文件头部第二个字节
//console.log( file.readback(-2) )
console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/File/IO/readback.md)

