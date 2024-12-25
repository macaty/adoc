[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 中文数�?
```aardio aardio
//中文数�?import console;
import string.chineseNumber;
var zh = string.chineseNumber();

//中文数�?console.log( zh.number("123456789000000000000") );
console.log( zh.number("123,456,789,000,000,000,000") );
console.log( zh.number("10,0000") );
console.log( zh.number("10_0000") );

console.log( zh.number(12305000.137) );
console.log( zh.number(1230_5000.137) );

//中文金额
var zh = string.chineseNumber('零壹贰叁肆伍陆柒捌玖','拾佰�?);
console.log(zh.money(12003089.35));
console.log(zh.number("010")); //票据日期补零

//中文时间
var zh = string.chineseNumber('〇一二三四五六七八九');
console.log(zh.datetime());
console.log(zh.date());
console.log(zh.time());
console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Text/chineseNumber.md)

