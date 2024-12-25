[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# string �?
请参考：

[数据类型 \- 字符串](../../../language-reference/datatype/datatype.html#varstring)

[类型转换](../../../language-reference/datatype/datatype.html#convert)

[取长操作符](../../../language-reference/operator/len.html)

[字符串连接操作符](../../../language-reference/operator/concat.html)

## 只读的字符串内存

aardio 从不改变现有的字符串，字符串内存是只读的，所有相同的字符串会指向同一内存地址，而修改字符串总是返回新的字符串�?
string 库所有的函数都是纯函数，遵守一个入�?参数)，一个出�?返回�?的原则，所以请不要忘记使用返回值接收被改变的字符串�?
```aardio aardio
var str = "abc";
string.upper(str); //这样的代码没有任何意�?也不会改变str

```

正确的写法如�?

```aardio aardio
var str = "abc";
str = string.upper(str);//不要忘记使用返回值接收被改变的字符串

```

这个规律适合所有截取字符串、改变字符串的函�?

## string 库文档索�?
[查找字符串](search.html)

[使用模式匹配查找与替换字符串](matching.html)

[拆分与合并字符串](part.html)

[解析特定格式文本](parsing.html)

[格式化文本](format.html)

[自文件快速读写文本或二进制字符串](file.html)

[随机字符串与随机数](rand.html)

[string 库参考](../../../library-reference/string/_.html)

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-guide/builtin/string/string.md)

