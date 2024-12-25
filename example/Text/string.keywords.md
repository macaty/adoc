[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 快速关键字搜索

```aardio aardio
//快速关键字搜索
import console;
import string.keywords;
var keywords = string.keywords('关键�?|keyword|Test',936);

//待搜索数�?var data = "
aaaaaaaaaaaaaaaaaaaaaaaaa
bbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbb
ccccccccccc关键�?
dddddddddddddddddddd Test ddddddddd
"

//转为 GBK 编码测试，当然也可以不指�?936 编码（前面关键字里也不要指定�?data = string.fromto(data,65001,936);

//查找所有包含任意关键字的文本行
var lines = keywords.anyMatchLines(data);

//显示结果，控制台同时兼容 UTF-8/系统默认 ANSI 编码（简体中文就�?936 �?console.log(string.join(lines,'\r\n'));

console.pause(true);

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Text/string.keywords.md)

