[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 Python 快速入�?
```aardio aardio
//aardio 调用 Python 快速入�?import console;
import py3;

//导入 Python 模块
var math = py3.import("math");

//调用 Python 函数�?var num = math.floor(22.3);

//在控制台输出数值�?console.log(num);

/*
请参�?Python 数据类型转换规则:
https://www.aardio.com/zh-cn/doc/library-guide/ext/python/conversion.html
*/

console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python 3.x/QuickStart.md)

