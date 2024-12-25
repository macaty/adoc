[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 快速入�?
```aardio aardio
//快速入�?import console;
import julia;

//调用 Julia 函数
var ret = julia.sqrt(2);

//导入 Julia 模块
julia.using("Base64");

//调用 Julia 函数
var data = julia.Base64.base64encode("测试一�?);

//转换 Julia 数据类型
var buf = julia.value.build(raw.buffer("abc"));

//显示类型�?console.log(julia.typeof(buf));

//制造代码错�?julia.eval("a = b(")

//查看 Julia 代码错误信息
console.log(julia.lasterr());

console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Julia/Julia.md)

