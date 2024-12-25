[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 控制台输�?
```aardio aardio
//控制台输�?import console;

/*
在导入前打开控制台，
Julia 才能向控制台输出内容（否则控制台上看不到输出�?*/
console.open();

import julia;

julia.eval("print(123)");

console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Julia/console.md)

