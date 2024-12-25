[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 自定义版�?
```aardio aardio
//自定义版�?import console.int;

/*
导入 julia 以前可以自定�?Julia 版本（必须是 3 组数值）�?支持 Julia 1.6 �?1.9.x，暂不支�?1.10 �?.10 的接口目前有 bug ）�?*/
string.setenv("JULIA_VERSION","1.6.1");

import julia;

//获取版本
var ver = julia.eval("string(VERSION)");

//输出版本
console.log(ver)

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Julia/version.md)

