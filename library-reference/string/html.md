[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# string.html 库模块帮助文�?
## string 成员列表

### string.html()

创建HTML解析�?参数请指定包含HTML代码的字符串,

调用string.xml解析HTML代码,用法与string.xml相同

但支持识别HTML空标签、省略闭合标签规�?
此对象不支持 table.tostring , console.dump 函数，不能跨线程传�?
[返回对象:stringXmlObject](#stringXmlObject)

## string.html 成员列表

HTML 简单解析器�?
严格的校�?HTML 语法正确性不是本模块的设计目标，

所以此解析器尽可能兼容错误,兼容�?HTML,SGML 的部分规�?

1. 不要求存在根标签

2. 尝试自动修正不配对的标记

3. 在有必要的时候尝试忽略大小写

4. 支持识别 HTML 空标签、省略闭合标签规�?
### string.html.escape()

将字符串中的 < \> " ' & �?HTML 标记字符编码为实体字符（entity）�?
如果参数为非 null 值则返回转换后的字符串�?
参数只能�?null 或字符串、buffer

### string.html.fromText(普通文�?

将普通文本转换为HTML

### string.html.ncr()

NCR 字符编码、HTML 实体字符还原�?UTF8 文本

### string.html.ncrEncode(str,pattern)

将字符串参数 @str 中以 @pattern 指定模式串所匹配的字符进�?NCR 编码�?
参数 @pattern 可用模式匹配语法指定要编码的字符，省略则默认�?":\|."�?
返回编码后的字符串�?
### string.html.removeTag(html,"script")

移除指定的html标记,支持不定个数的标记参�?
### string.html.toText(HTML代码)

将HTML代码转换为文�?
### string.html.toXml(HTML代码)

�?HTML 代码转换�?XML 文本

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/string/html.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/string/html.md')

