[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# string.template 库模块帮助文�?
## string 成员列表

### string.template

字符串模�?
### string.template()

[返回对象:stringTemplateObject](#stringTemplateObject)

### string.template(模板字符�?模板匹配规则)

可选使用模式匹配语法指定参数匹配规�?
默认匹配规则�?\\${(.+?)}",匹配形如 ${参数名} 的参�?
## stringTemplateObject 成员列表

### stringTemplateObject.?

可用 $模板参数�?格式指定模板参数的默认�?
### stringTemplateObject.format

```aardio aardio
stringTemplateObject.format(
    参数�?= �?*可选指定任意多个参数键值对用于替换模板参数*/;
)

```

### stringTemplateObject.template

```aardio aardio
stringTemplateObject.template = /***
    ${模板参数}/*根据预设的格式标明参�?/
***/

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/string/template.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/string/template.md')

