[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# 连接运算�?
参考： [字符串](../datatype/string.html)

对两个操作数进行字符串连接操作�?
如果操作数不是字符串，aardio 将尝试自动转换为字符串，如果转换失败则会报错�?
运算符说明`++`连接运算�?
![](../../icon/info.gif) 要特别注�?`+` 运算符也具有连接字符串的作用�?
- 引号（双引号、单引号、反引号）前后的 `+` 运算符将自动转换为字符串连接运算�?`++` �?- 如果 `+` 运算符的两个操作数都是字符串，且其中任一操作数无法转换为数值则进行字符串连接操作。不应依赖此规则做字符串连接，明确写�?`++` 可以避免不必要的转换，也可避免不必要的误操作�?
例如�?
```aardio aardio
import console.int;

// str �?“hello world�?var str = "hello " ++ "world";

// str �?"12"，表达式自动转换�?1 ++ "2"
var str = 1 + "2";

// str 为数�?3�? �?" 号被括号分开
var str = 1 + ("2");

console.log(str);

```

除了在引号（双引号、单引号、反引号）前后可以用 `+` 替代 `++`，其他情况下应当明确�?`++` 以避免误操作与不必要的转换过程�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/language-reference/operator/concat.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/language-reference/operator/concat.md')
