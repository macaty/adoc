[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# string.database 库模块帮助文�?
## string 成员列表

### string.database

用于解析、读�?CSV（Comma Separated Values），TXT 格式数据库�?
注意文本数据规范不统一，不同的程序解析结果可能有差异�?
用法请参考：范例程序 / 数据�?/ csv / string.database

创建 TTXT，CSV 格式数据库对象�?
### string.database()

[返回对象:stringDatabaseObject](#stringDatabaseObject)

### string.database(columnSeparator,quote,commentChar)

创建 TXT，CSV 格式数据库对象�?
参数 @columnSeparator 指定列分隔符，省略则默认使用逗号作为分隔符�?
参数 @quote 指定包含引用字段（含有列分隔符）的引号，省略则使用双引号�?
参数 @commentChar 指定注释符号，默认不指定并禁用注释�?
## stringDatabaseObject 成员列表

### stringDatabaseObject.comment

最后一次解�?CSV 读取的注释�?
需要在使用属性或构造参�?commentChar 先指定注释标记�?
### stringDatabaseObject.commentChar

用于指定行注释开始标记，注释只在行首有效（避免与数据混淆）�?
一般都使用"#"符号，但不是所�?CSV 解析器都支持注释�?
默认值为 null，也就是不启用注释�?
### stringDatabaseObject.dataTable

对象本身存储的数据表�?
parse 函数解析得到的数组会赋值并替换此属性�?
push 函数则默认向此数据表添加数据�?
stringify,stringifyA 函数在不指定参数时使用此数据表作为参�?
### stringDatabaseObject.each(文件路径)

```aardio aardio
for tab in stringDatabaseObject.each("文件路径.csv") {
    /*逐行读取 CSV 文件，tab 为当前读取行解析后的列数�?/
}

```

### stringDatabaseObject.load

加载并解析文�?
### stringDatabaseObject.load(文件路径,代码�?

加载并解析文件，返回数组,

文件开头有 UTF-8 BOM 则以 UTF-8 编码读入内容,

否则以参�?@2 指定的编码读入并转换�?UTF-8 编码�?
参数 @2 省略时默认值为 0，表示当前默�?ANSI 编码

### stringDatabaseObject.parse

解析数据并返回得到的数组

### stringDatabaseObject.parse(文本)

解析数据并返回得到的数组�?
对象�?dataTable 属性也会被赋值并替换为这里返回的数组

### stringDatabaseObject.parseComment(pattern)

自注释中提取并解析字段声明�?
参数 pattern 使用模式匹配语法指定提出规则�?
默认�?`<\a+\:\s*>?(\N+)\s*$` ，也就是取最后一行注释�?
### stringDatabaseObject.push

添加数据到对象的 dataTable 属性指向的数据�?
### stringDatabaseObject.push(...)

添加数据到对象的 dataTable 属性指向的数据�?
参数 @1 如果是表，则所有参数都作为数据行添加到 dataTable 数据�?
否则所有参数合并为一行数据并添加�?dataTable 数据�?
之后可以调用 stringify 函数生成文本

### stringDatabaseObject.quote

指定用于包含列的引号，默认为双引号�?
仅在字段包含分隔符时才会将字段包含在引号内�?
### stringDatabaseObject.save

�?UTF-8 编码写入文件

### stringDatabaseObject.save(文件路径,数据数组,是否追加)

在指定文件写�?UTF-8 BOM�?
然后将数据以 UTF-8 编码、CSV 格式写入文件�?
如果不指定数据数组参数，则使用之前调�?push 函数添加的数据�?
参数 @3 如果�?true 则保留原来的文件内容�?
### stringDatabaseObject.saveA

�?ANSI 编码写入文件

### stringDatabaseObject.saveA(文件路径,数据数组,是否追加)

将数据以 ANSI 编码、CSV 格式写入文件

如果不指定数据数组参数，则使用之前调�?push 函数添加的数据�?
参数 @3 如果�?true 则保留原来的文件内容�?
### stringDatabaseObject.separator

列分隔符，默认为逗号

### stringDatabaseObject.stringify

数据表转换为 UTF-8 文本

### stringDatabaseObject.stringify(数据数组)

数据表转换为 UTF8 文本

如果不指定参�?则使用对象的 dataTable 属性作为参�?
### stringDatabaseObject.stringifyA

数据表转换为 ANSI 文本

### stringDatabaseObject.stringifyA(数据数组)

数据表转换为 ANSI 文本

如果不指定参�?则使用对象的 dataTable 属性作为参�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/string/database.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/string/database.md')

