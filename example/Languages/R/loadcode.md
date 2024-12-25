[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 R 语言 - 嵌入模板

```aardio aardio
//aardio 调用 R 语言 - 嵌入模板
import console.int;
import process.r;

//执行 R 代码，支持模板语法：
//https://www.aardio.com/zh-cn/doc/language-reference/templating/syntax.html
var prcs = process.r.loadcode(`write("<?

//可以�?R 代码中嵌�?aardio  代码
if(_WIN10_LATER){
    print("新系�?,owner.模板参数�?
}
else {
    print("旧系�?,owner.模板参数�?
}

?>",file=".data.txt");`,{
    模板参数�?= "参数�?
})

prcs.logResponse();

console.log(string.load("/.data.txt"))

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/R/loadcode.md)

