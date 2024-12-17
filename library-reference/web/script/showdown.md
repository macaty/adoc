[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# web.script.showdown 库模块帮助文�?
## web.script.showdown 成员列表

Markdown 解析器，基于 JavaScript 开源组�?Showdown �?
### web.script.showdown.Converter()

创建解析器�?
可选使用一个表参数指定解析选项�?
可用选项请参�?Showdown 文档�?
[返回对象:ShowdownConverterObject](#ShowdownConverterObject)

### web.script.showdown.getOption()

获取指定选项

### web.script.showdown.getOptions()

获取可用于读写全部解析选项的对�?
### web.script.showdown.setFlavor()

设置默认语法风格�?
默认已设�?'github'，即 GFM (GitHub Flavored Markdown)�?
### web.script.showdown.setOption('optionKey','value')

设置全局选项�?
## ShowdownConverterObject 成员列表

### ShowdownConverterObject.getOption()

获取指定选项

### ShowdownConverterObject.getOptions()

获取可用于读写全部解析选项的对象�?
### ShowdownConverterObject.makeHtml()

将参�?@1 指定�?Markdown 文本转换�?HTML

### ShowdownConverterObject.setFlavor('github')

设置语法风格，默认已设为 'github'�?
### ShowdownConverterObject.setOption('optionKey','value')

设置解析选项�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/web/script/showdown.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/web/script/showdown.md')

