[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# string.list 库模块帮助文�?
## string 成员列表

### string.list

字符串列�?
创建字符串列�?
### string.list()

[返回对象:stringlistObject](#stringlistObject)

### string.list(字符�?行分隔符,键值分隔符,引用�?

第一个参数也可以是文件路�?所有参数可�?
行分隔符�?\\s","\\s+",或开始于"\["字符时使用模式匹配语�?
如果使用了模式匹�?可在tostring的参数中指定拼接为字符串的行分隔�?不指定使用空格拼�?

行分隔符不指定时默认为回车换�?

键值分隔符默认为等�?

引用符必须指字含两个单字节字符的字符�?例如两个引号�?
对于包含了分隔符的�?在生成字符串时自动置入引用符内�?
关于引用符请参考getConfiguration()函数说明�?
这里如果指定引用符则覆盖默认的quoteChar,quoteChars配置

## stringlistObject 成员列表

### stringlistObject.assign

```aardio aardio
stringlistObject.assign(
    �?= �?
)

```

### stringlistObject.each

```aardio aardio
for i,k,v in stringlistObject.each() {
    io.print("顺序:"+i,"名字:"+k,"�?"+v )
}

```

### stringlistObject.find("字符串参�?)

查找指定键所在位�?忽略大小�?
支持使用多个能有数指定多个查找键�?此函数将逐个查找,

找到即返回返回三个�? 位置索引,键名,键�?
### stringlistObject.getConfiguration()

返回配置

[返回对象:stringlistcfgObject](#stringlistcfgObject)

### stringlistObject.load("字符串参�?)

加载配置文件

### stringlistObject.load()

[返回对象:stringlistObject](#stringlistObject)

### stringlistObject.remove("字符串参�?)

查询并移除第一个找到的键名与键值，键名忽略大小写�?
如果只是�?string.list 对象的下标设置指定键�?null 值，并不会移除键名�?
### stringlistObject.save("字符串参�?)

保存配置文件

### stringlistObject.save()

保存配置文件

[返回对象:stringlistObject](#stringlistObject)

## stringlistcfgObject 成员列表

### stringlistcfgObject.lineDelimiter

行分隔符,默认为回车换�?
### stringlistcfgObject.nameValueSeparator

键值对分隔�?默认为等�?
### stringlistcfgObject.quoteChar

生成字符串使用的引用符号,默认为双引号

如果某个键名对应的字符串值包含换行符,且没有包含在其他引用符内,

在转换为文本格式的字符串列表�?自动添加此引用符

### stringlistcfgObject.quoteChars

解析字符串时支持的引用符�?
默认为单双引号、大中小括号,

可设为空表清空所有引用符�?

引用符号内忽略行分隔�?
### stringlistcfgObject.reserve

保留名字�?不可修改

### stringlistcfgObject.reserveData

保留数据,不可手动修改

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/string/list.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/string/list.md')

