[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# string.builder 库模块帮助文�?
## string 成员列表

### string.builder

字符串生成器

创建的对象内部使用动态指�?并负责自动释放动态指�?
要切记对象虽然可以在API中转换为普通指针使�?
但任何可能导致自动调整内存大小操作都有可能改变动态指针指向的内存,并使原指针失�?
### string.builder()

创建字符串生成器�?
可选在参数中指定预分配内存大小

生成器对象可使用+,++连接字符串、buffer、结构体,或使用\[\]操作符取字节�?

此对象可用于拼接字符串，并自动调整内存大�?

在大字符串频繁拼接时可明显提升速度�?
小字符串少量拼接不需要使用些对象

[返回对象:stringbuilderObject](#stringbuilderObject)

## stringbuilderObject 成员列表

### stringbuilderObject.append(追加数据,追加长度)

追加数据可以是字符串，buffer，或其他指针

如果参数不是指针追加长度可省�?
此函数可能改变内部动态指针�?
### stringbuilderObject.appendf("C格式化串",...)

使用printf函数格式化文�?
此函数可能改变内部动态指针�?
### stringbuilderObject.assign()

重置初始�?
参数可以是字符串，buffer，或结构�?
此函数可能改变内部动态指针�?
### stringbuilderObject.capacity()

返回预分配内存大�?
释放指针后此函数返回0

### stringbuilderObject.eachIndexOf(查找内容)

```aardio aardio
for(i in stringbuilderObject.eachIndexOf(/*查找内容*/)){

}

```

### stringbuilderObject.empty()

存储内容是否为空

### stringbuilderObject.free()

释放内存

此函数设置内部动态指针值为null

释放动态指针以�?仍然可以调用reserve函数重新分配内存

### stringbuilderObject.fromUtf16(转换字符�?目标编码)

自UTF16编码转换为多字节编码字符串，默认为UTF8

参数@1以字符计数，�?个字节为一个单�?字符数只能为数值，省略时默认值为-1

字符数为-1表示查找 `'\u0000'` 终止符获取可打印文本长度

### stringbuilderObject.indexAny("字符串参�?)

参数用一个字符串指定要查找的单字节字�?
返回任意字符最初出现的位置,找不到返回值为�?
### stringbuilderObject.indexOf(查找内容,查找开始位�?

普通字符串查找

不使用模式匹配语�?
### stringbuilderObject.leftString()

从左侧截取参数指定长度的字符�?
返回字符串对�?参数可用负数表示右侧截取位置

不会改变内部动态指针�?
### stringbuilderObject.reserve()

调整预分配内存大�?返回自身

小于存储内容大小时则设为存储内容大小

�?时设�?024

此函数可能改变内部动态指针�?
释放动态指针以�?仍然可以调用此函数重新分配内�?
[返回对象:stringbuilderObject](#stringbuilderObject)

### stringbuilderObject.resize()

调整存储内容大小

此函数可能改变内部动态指针�?
### stringbuilderObject.rightString()

从右侧截取参数指定长度的字符�?
返回字符串对�?参数可用负数表示左侧截取位置

不会改变内部动态指针�?
### stringbuilderObject.size()

返回存储内容大小

释放指针后此函数返回0

### stringbuilderObject.str

转换为纯文本字符�?
如果需要转换为二进制字符串,直接使用 tostring 函数转换string.builder对象即可

### stringbuilderObject.str(是否unicode,偏移)

去掉尾部多余终结符转换为纯文本字符串,参数可省�?偏移默认�?

参数@1为true反回字符串标记会设置UTF-16标记,否则设为UTF-8标记

### stringbuilderObject.subString(开始位�?结束位置)

截取字符�?
返回字符串对象，参数不能为负�?
开始位置省略则表示1，结束位置省略则表示存储内容尾部

不会改变内部动态指针�?
### stringbuilderObject.toUtf16(转换字节�?源编�?

转换并返回UTF16编码字符�?
字节数可省略,默认�?1

字节数为-1时表示查�?`'\0'` 终止符自动获取长�?
### stringbuilderObject.tokenize(分割�?

```aardio aardio
for(i in stringbuilderObject.eachIndexOf("/*单字节分割符*/")){

}

```

### stringbuilderObject.trim()

清除两侧空白字符

可选用一个字符串指定要清除的单字节字�?
### stringbuilderObject.trimleft()

清除左侧空白字符

可选用一个字符串指定要清除的单字节字�?
### stringbuilderObject.trimright()

清除右侧空白字符

可选用一个字符串指定要清除的单字节字�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/string/builder.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/string/builder.md')

