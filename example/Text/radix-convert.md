[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 进制转换

```aardio aardio
//进制转换
//用格式化函数可以实现数字的进制转�?//参考文档： https://www.aardio.com/zh-cn/doc/library-guide/builtin/string/format.html

import console;

//数字转换为二进制字符�?var str = string.format("%b",23 );
console.print(str);

//二进制字符串转换为数�?var n = tonumber(str,2);

//数字转换为八进制字符�?str = string.format("%o",23 );
console.print(str);

//八进制字符串转换为数�?n = tonumber(str,8);

//数字转换为十六进制字符串
str = string.format("%x",23 );
console.print(str);

//tostring 也可以用参数@2指定的进制转换参数@1指定的数值�?str = tostring(23,16);
console.print(str);

//十六进制字符串转换为数字
n = tonumber(str,16);
console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Text/radix-convert.md)

