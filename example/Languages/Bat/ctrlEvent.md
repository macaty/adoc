[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 发�?Ctrl+C

```aardio aardio
//发�?Ctrl+C
import console
import process.popen

var prcs = process.popen("ping 127.0.0.1 -n 10 ")
for( all,out,err in prcs.each() ){
    console.log( out,err );
    prcs.ctrlEvent(0);
}

console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Bat/ctrlEvent.md)

