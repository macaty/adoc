[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: TOML解析�?
```aardio aardio
//TOML解析�?import console;
import string.toml;

//TOML 快速入�? https://quickref.me/zh-CN/docs/toml.html
var str = string.toml.stringify({abc=123,d={1,2,3}});
console.log( str );

import process.code;
process.code("~\lib\string\toml\.res");
console.pause(true);

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Rust/toml.md)

