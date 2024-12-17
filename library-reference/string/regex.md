[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# string.regex 库模块帮助文�?
## string 成员列表

### string.regex

VBS正则表达式支持库

### string.regex("字符串参�?)

创建正则表达�?
### string.regex()

[返回对象:vbsrgxObject](#vbsrgxObject)

## vbsrgxMatchObject 成员列表

### vbsrgxMatchObject.FirstIndex

位置

### vbsrgxMatchObject.Length

长度

### vbsrgxMatchObject.SubMatches(索引)

匹配子串(用括号指定的分组)

### vbsrgxMatchObject.Value

匹配结果

## vbsrgxObject 成员列表

### vbsrgxObject.find(目标字符�?

搜索字符�?成功返回true

### vbsrgxObject.find(目标字符�?".+")

搜索字符�?成功返回true

### vbsrgxObject.global

是否全局匹配

只能设为0�?

默认�?表示启用全局匹配

### vbsrgxObject.gmatch()

[返回对象:vbsrgxMatchObject](#vbsrgxMatchObject)

### vbsrgxObject.gmatch(str)

```aardio aardio
for i,smatch in regex.gmatch(/*要匹配的字符�?/){

}

```

### vbsrgxObject.gmatch(str,pattern)

```aardio aardio
for i,smatch in regex.gmatch(/*要匹配的字符�?/,".+"){

}

```

### vbsrgxObject.ignoreCase

是否忽略大小�?
### vbsrgxObject.pattern

设置或返回用于搜索的正则表达�?
### vbsrgxObject.replace(源字符串,替换字符�?

替换

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/string/regex.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/string/regex.md')

