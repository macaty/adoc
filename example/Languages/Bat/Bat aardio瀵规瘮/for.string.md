[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 批处理与 aardio 对比 - for 命令之文本分�?
```aardio aardio
//批处理与 aardio 对比 - for 命令之文本分�?import console
import process.batch;

//批处�?for 遍历并拆分字符串
var bat = process.batch(`
@echo off
for %%i in (abc,def,xyz) do echo %%i
`)
console.log(bat.read(-1))

/*
用aardio 实现与上面相同的功能,
循环遍历用空格键、跳格键(tab)、逗号、分号或等号拆分出来的字符串�?string.lines 的第 @2 个参数指定分隔符，支持类正则表达式的 aardio 模式匹配语法�?*/
for( line in string.lines("abc,def,xyz","[\s,;=]") ){
    //注意 aardio 里循环变量名不需要在前面�?%，也不限制只能使�?6个字�?    console.log(line)
}

//创建测试文件
string.save("/test.txt","abc,def
123,456" )

//批处�?for 遍历并按行拆分字符串
var bat = process.batch(`
@echo off
for /f "usebackq delims=, tokens=1,2" %%i in ("test.txt") do echo %%i,%%j
`)
//注意文件路径如果有空格必须包含在引号�?//如果要用引号包含路径，就必须加上 usebackq，usebackq的意思是用反引号包含命令，单引号包含字符串，然后双引号就可以包含文件路径而不是字符串�?console.log(bat.read(-1));
console.more(1);

//aardio 需要先读文件到字符�?var str = string.load("/test.txt")

//参数@3指定delims，可以用强大的模式匹配语法指定分隔符
for tokens in string.lines(str,,",") {
    //tokens是一个数组，可以�?string.join 任意拼接数组中指定范围的元素实现批处�?tokens=n-m 的效�?    console.log(tokens[1],tokens[2])
}

/*
aardio 提供了大量的字符串函数，以及强大的模式匹配功能，
可以实现非常复杂的文本解析功能，例如标准库中解析JSON�?web.json，解析XML,HTML�?string.xml,string.html等等
*/

//例如我们也可以用 string.each 实现上面的功�?for a,b in string.each(str,"([^,]+),(.+)"){
    console.log(a,b)
}

//删除测试文件
io.remove("/test.txt")
console.pause()

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Bat/Bat aardio对比/for.string.md)

