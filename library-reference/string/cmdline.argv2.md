[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# string.cmdline.argv2 库模块帮助文�?
参数解析规则

命令行基础转义规则请参�?string.cmdline 文档说明�?解析时忽略索引为 0 的参数，解析 \_CMDLINE 时应在前面补上空格避免忽略第一个参数�?
所有非命名参数都会添加到返回参数表的数组成员�?\-\- �?// 之后的参数都视为非命名参数�?
命名参数解析规则如下�?
1、参数名区分大小�?2、以斜杠或短横线开始的前导参数作为键名(键名移除一个或多个相同的前导字符，区分大小�?�?如果前导参数包含等号，则以等号拆分为键值对，等号前后不应有空格�?否则检查下一参数如果没有相同的首字符则设为此键名对应的值，
如果一个前导参数没有指定值，则默认值为空字符串（逻辑值为 true）�?3、单�?- 开头的命名参数解析为短参数�?短参数可以用空格分隔参数值，也可以省略分隔符（等号不作为分隔符）�?
可在�?2 个调用参数中指定一�?@option 选项表�?@option 的所有键名用于指定待解析的命令行参数名字�?@option 预定义的单字符或多字符名字可作为短参数名、长参数名使用�?@option 预定义的单字母参数名允许作为短参数名合并到一个参数段�?
@option 中参数名对应的值可以为任何�?false 值�?如果 @option 表中定义的值是函数，则每次解析对应名称参数时都会回调该函数�?回调参数 @1 为解析得到的参数值，而回调参�?@2 为将要返回的解析结果（参数表）�?
示例�?
```aardio aardio
var argv = string.cmdline.argv2(` -a -deffff  "c:\test.txt" "c:\test2.txt"`,{
    m = true;
    n = function(value,argv){

    }
});

console.dump(argv)

```

## string.cmdline 成员列表

### string.cmdline.argv2

解析命令行并返回参数表�?
string.cmdline.argv 函数的增强版本�?
命令行基础转义规则请参�?string.cmdline 文档说明�?
解析时忽略索引为 0 的参数，解析 \_CMDLINE 时应在前面补上空格避免忽略第一个参�?
### string.cmdline.argv2("命令�?,option)

所有非命名参数都会添加到返回参数表的数组成员�?
\-\- �?// 之后的参数都视为非命名参数�?
命名参数解析规则如下�?
1、参数名区分大小�?
2、以斜杠或短横线开始的前导参数作为键名(键名移除一个或多个相同的前导字符，区分大小�?�?
如果前导参数包含等号，则以等号拆分为键值对，等号前后不应有空格�?
否则检查下一参数如果没有相同的首字符则设为此键名对应的值，

如果一个前导参数没有指定值，则默认值为空字符串（逻辑值为 true）�?
3、单�?- 开头的命名参数解析为短参数�?
短参数可以用空格分隔参数值，也可以省略分隔符（等号不作为分隔符）�?
可在�?2 个调用参数中指定一�?@option 选项表�?
@option 的所有键名用于指定待解析的命令行参数名字�?
@option 预定义的单字符或多字符名字可作为短参数名、长参数名使用�?
@option 预定义的单字母参数名允许作为短参数名合并到一个参数段�?
@option 中参数名对应的值可以为任何�?false 值�?
如果 @option 表中定义的值是函数，则每次解析对应名称参数时都会回调该函数�?
回调参数 @1 为解析得到的参数值，而回调参�?@2 为将要返回的解析结果（参数表）�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/string/cmdline.argv2.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/string/cmdline.argv2.md')
