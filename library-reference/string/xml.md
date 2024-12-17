[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# string.xml 库模块帮助文�?
## string 成员列表

### string.xml()

[返回对象:stringXmlObject](#stringXmlObject)

### string.xml(xml字符�?

创建 XML 对象�?
此对象不支持 table.tostring , console.dump 函数，不能跨线程传递�?
严格的校验XML语法正确性不是本模块的义务和目标,

所�?此解析器尽可能兼容错�?兼容了HTML,SGML的部分规�?

1、不要求存在根标�?
2、尝试自动修正不配对的标�?
3、在有必要的时候尝试忽略大小写

## string.xml 成员列表

简�?XML 解析器�?
严格的校�?XML 语法正确性不是本模块的设计目标，

所以此解析器尽可能兼容错误，兼容了 HTML，SGML 的部分规�?

1. 不要求存在根标签

2. 尝试自动修正不配对的标记

3. 在有必要的时候尝试忽略大小写�?
### string.xml.escape()

将字符串中的 < \> " ' & �?XML 标记字符编码为实体字符（entity）�?
如果参数为非 null 值则返回转换后的字符串�?
参数只能�?null 或字符串、buffer

### string.xml.ncr()

NCR 字符编码、HTML实体字符还原�?UTF8 文本

### string.xml.ncrEncode(str,pattern)

将字符串参数 @str 中以 @pattern 指定模式串所匹配的字符进�?NCR 编码�?
参数 @pattern 可用模式匹配语法指定要编码的字符，省略则默认�?":\|."�?
返回编码后的字符串�?
## stringXmlObject 成员列表

### stringXmlObject.?

属性或子节点数�?
[返回对象:stringXmlObject](#stringXmlObject)

### stringXmlObject.codepage

源文本代码页

### stringXmlObject.eachAttribute()

```aardio aardio
for( k,v in stringXmlObject.eachAttribute() ){
    /*遍历节点所有属�?k为属性名,v为属性�?/
}

```

### stringXmlObject.eachChild()

[返回对象:stringXmlObject](#stringXmlObject)

### stringXmlObject.eachChild(标签�?

```aardio aardio
for(index,tagName,childCount,xNode in stringXmlObject.eachChild(/*标签名，区分大小�?/) ){
    io.print( index,tagName,childCount,xNode )
}

```

### stringXmlObject.eachQuery(查询参数�?

```aardio aardio
for ele in stringXmlObject.eachQuery(tagName="img"/*搜索并遍历节点对�?

参数@1指定一个表对象�?该参数表可包含一个或多个键值，用于匹配节点的属性�?
可使用tagName属性指定节点的标签�?
可使用parent属性指定开始查询节点的父节点，parent可以是ID或者节点对象�?属性值使�?string.cmpMatch函数进行比对�?等价于调用string.cmp函数进行忽略大小写的比较,
并且在失败后调用 string.match函数使用模式匹配语法进行比较

注意在匹配节点属性时有几个例外：
parent属性不使用模式匹配进行比对�?tagName,id,name属性如果匹配值不含标点则使用忽略大小写的完全比对（禁用模式匹配和部分匹配�?/){

}

[返回对象:stringXmlObject](#stringXmlObject)

```

### stringXmlObject.encoding

源文本字符集

### stringXmlObject.enumNodes(枚举函数,搜索标签�?

```aardio aardio
stringXmlObject.enumNodes(
    function(parentElement,index,tagName,childCount,xNode){

    },/*可选指定要查找的标签名（tagName），忽略大小�?回调函数返回�?null 值时退出枚举，并返回回调函数的所有返回�?/
)

```

### stringXmlObject.getAttribute()

取属性�?

参数中指定属性名�?属性名忽略大小�?

如果通过下标或成员操作符直接获取属性时区分大小写的

### stringXmlObject.getEle("字符串参�?)

获取指定id的节点对�?

参数指定节点id,忽略大小�?支持模式匹配规则

### stringXmlObject.getEles("字符串参�?)

获取所有指定相同name的节点对�?返回数组,

即使找不到节�?也会返回空数�?

参数指定节点name,忽略大小�?支持模式匹配规则

### stringXmlObject.getParent()

获取父节�?
### stringXmlObject.innerText()

返回节点内部文本或CDATA文本

### stringXmlObject.innerXml()

将子节点转换XML文本,

如果参数@1为true则缩进格式化返回的xml文本,

可选在参数@2中自定义换行�?
### stringXmlObject.outerXml()

转换为XML文本,

如果参数@1为true则缩进格式化返回的xml文本,

可选在参数@2中自定义换行�?
### stringXmlObject.pushElement()

[返回对象:stringXmlObject](#stringXmlObject)

### stringXmlObject.pushElement(节点属性表)

```aardio aardio
stringXmlObject.pushElement(
    tagName =
    cdata =
    text = /*注意text,cdata,tagName三个属性只能指定一�?
可选使用参数@2指定新增节点的位�?不指定则添加到子节点数组尾部,
返回新增的节点对�?/
)

```

### stringXmlObject.pushXml()

将字符串参数@1中指定的XML添加到当前节点的子节�?

可选用参数@2指定新节点的位置,不指定则添加到子节点数组尾部,

返回新增XML中最后一个根节点

[返回对象:stringXmlObject](#stringXmlObject)

### stringXmlObject.queryEle(查询参数�?

搜索节点对象,参数@1指定一个表对象�?
该参数表可包含一个或多个键值，用于匹配节点的属性�?

可使用tagName属性指定节点的标签�?

可使用parent属性指定开始查询节点的父节点，parent可以是ID或者节点对象�?
属性值使�?string.cmpMatch函数进行比对�?
等价于调用string.cmp函数进行忽略大小写的比较,

并且在失败后调用 string.match函数使用模式匹配语法进行比较

注意在匹配节点属性时有几个例外：

parent属性不使用模式匹配进行比对�?
tagName,id,name属性如果匹配值不含标点则使用忽略大小写的完全比对（禁用模式匹配和部分匹配�?
### stringXmlObject.queryEles( 查询参数�?

搜索节点对象,该函数返回的是一个数�?

即使找不到节�?此函数也会返回一个空数组,

参数@1指定一个表对象�?
该参数表可包含一个或多个键值，用于匹配节点的属性�?

可使用tagName属性指定节点的标签�?

可使用parent属性指定开始查询节点的父节点，parent可以是ID或者节点对象�?
属性值使�?string.cmpMatch函数进行比对�?
等价于调用string.cmp函数进行忽略大小写的比较,

并且在失败后调用 string.match函数使用模式匹配语法进行比较

注意在匹配节点属性时有几个例外：

parent属性不使用模式匹配进行比对�?
tagName,id,name属性如果匹配值不含标点则使用忽略大小写的完全比对（禁用模式匹配和部分匹配�?
### stringXmlObject.queryEles()

[返回对象:stringXmlObject](#stringXmlObject)

### stringXmlObject.remove()

如果存在父节�?在父节点中移除此节点

### stringXmlObject.tagName

节点标签�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/string/xml.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/string/xml.md')

