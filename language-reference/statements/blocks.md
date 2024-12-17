[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# 语句�?block)

参�? [基本语法 \- 语句](../basic-syntax.html#statement)

## 语句�?
语句块由一组顺序执行的语句组成�?
使用 `{` 符号标记语句块开始、用 `}` 符号标记语句块结束�?`{}` 要首尾配对使用�?
示例�?
```aardio aardio
{
    var str = "我是局部变�? ;

    {
        var str2 = "一个语句块可以嵌套另一个语句块" ;
    } ;

};

import console;
console.log(str);  //输出：null

```

一个语句块可以嵌套另一个语句块。为了清晰地表示嵌套的层次，建议在增加嵌套层次同时使�?tab 制表符增加行缩进以示区分�?[](../../icon/warning.gif) 建议不要使用过多层次的嵌套语句块，以避免降低代码可读性�?
aardio 也允许使�?`begin` 关键字标记语句块开始、用 `end` 关键字标记语句块结束�?`begin` �?`end` 也要配对使用）。aardio 提供这个替代写法的初衷是为了在语句块嵌套过深时使用不同的标记区分不同的语句块，但这种情况原本就应当尽量避免。aardio 建议大家使用更简洁的 `{}` 包含语句块，而不是使�?`begin` �?`end` 的替代写法�?
## 语句块与局部变�?
在语句块中可以使�?var 语句定义局部变量�?
参考： [var 语句](assignment.html#var)

语句块中的局部变量拥有块级作用域，并用拥有最高存取优先级�?
aardio 根据标志符查�?命名对象"的顺序依次为�?
1. 当前语句块局部变量�?2. 在上层语句块就近搜索局部变量�?3. 如果有外层函数，则继续向上就近搜索所有外层函数的局部变量�?4. 搜索当前名字空间( self )的成员变量�?
要特别注意：

> 如果当前名字空间不是全局名字空间，aardio 默认不会到全局表查找命名对象，除非标识符指向一个全局有效的命名对象（全局常量、保留常量、保留函数名）或使用 `..` 操作符明确指定仅在全局表中查找命名对象 �?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/language-reference/statements/blocks.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/language-reference/statements/blocks.md')

