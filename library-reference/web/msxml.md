[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# web.msxml 库模块帮助文�?
## web 成员列表

### web.msxml

MSXML 支持�?
### web.msxml()

创建 XML 文档对象,可选在参数中指�?URL �?XML 文本,

如果�?XML 文本,可选使用参数@2指定内码

[返回对象:msxmlObject](#msxmlObject)

## msXmlAttributeNodeObject 成员列表

### msXmlAttributeNodeObject.nodeName

获取特定结点类型的名�?
### msXmlAttributeNodeObject.nodeType

获取所需结点的类�?
### msXmlAttributeNodeObject.nodeValue

设置或获取结点的�?
### msXmlAttributeNodeObject.specified

获取是否指定了该属�?
### msXmlAttributeNodeObject.value

设置或获取对象的�?
## msXmlDocObject 成员列表

### msXmlDocObject.createNode()

[返回对象:msXmlNodeObject](#msXmlNodeObject)

### msXmlDocObject.createNode(类型,名称,名字空间)

创建节点

### msXmlDocObject.documentElement

[返回对象:msXmlNodeObject](#msXmlNodeObject)

### msXmlDocObject.getElementsByTagName("\*tagName")

根据标签名返回节�?
### msXmlDocObject.getElementsByTagName()

[返回对象:msXmlNodeObject](#msXmlNodeObject)

### msXmlDocObject.nodeFromId("字符串参�?)

根据ID返回节点

### msXmlDocObject.nodeFromId()

[返回对象:msXmlNodeObject](#msXmlNodeObject)

### msXmlDocObject.parseError

返回错误信息

### msXmlDocObject.parseError.errorCode

该错误代�?
### msXmlDocObject.parseError.line

错误行号

### msXmlDocObject.parseError.linePos

错误列号

### msXmlDocObject.parseError.reason

错误信息

### msXmlDocObject.parseError.srcText

出错XML代码

### msXmlDocObject.readyState

0－未初始化�?－正在加载�?－已加载�?－交互中�?－已完成

### msXmlDocObject.selectNodes("字符串参�?)

查询节点�?
返回 COM 数组，使�?length 属性获取数组长度�?
返回数组起始索引�?0（aardio 普通数组起始索引为 1�?
### msXmlDocObject.setProperty("SelectionLanguage","XPath")

设置属�?
### msXmlDocObject.validateOnParse

解析XML是否验证合法�?
## msXmlNodeObject 成员列表

### msXmlNodeObject.appendChild(子节�?

添加子节�?
### msXmlNodeObject.attributes()

[返回对象:msXmlAttributeNodeObject](#msXmlAttributeNodeObject)

### msXmlNodeObject.attributes().nodeValue

属性�?
### msXmlNodeObject.attributes(0)

对象标签属性的集合指定位置的对�?
### msXmlNodeObject.childNodes()

[返回对象:msXmlNodeObject](#msXmlNodeObject)

### msXmlNodeObject.cloneNode()

克隆节点

[返回对象:msXmlNodeObject](#msXmlNodeObject)

### msXmlNodeObject.cloneNode(true)

完全克隆节点

[返回对象:msXmlNodeObject](#msXmlNodeObject)

### msXmlNodeObject.firstChild

返回第一个节�?
[返回对象:msXmlNodeObject](#msXmlNodeObject)

### msXmlNodeObject.getAttribute("属性名属性名")

获取属�?
也可以直接写 var 返回�?ele.属性名�?
### msXmlNodeObject.getAttributeNode("字符串参�?)

获取attribute对象

### msXmlNodeObject.getAttributeNode()

[返回对象:msXmlAttributeNodeObject](#msXmlAttributeNodeObject)

### msXmlNodeObject.getElementsByTagName("字符串参�?)

根据标签名返回节�?
### msXmlNodeObject.getElementsByTagName()

[返回对象:msXmlNodeObject](#msXmlNodeObject)

### msXmlNodeObject.getText()

返回文本属�?
### msXmlNodeObject.hasChildNodes()

对象是否有子对象的�?
### msXmlNodeObject.insertBefore(插入新节�?子节�?

插入子节�?
### msXmlNodeObject.lastChild

返回最后一个节�?
[返回对象:msXmlNodeObject](#msXmlNodeObject)

### msXmlNodeObject.length

集合中的节点个数

### msXmlNodeObject.nextNode

下一个节�?
[返回对象:msXmlNodeObject](#msXmlNodeObject)

### msXmlNodeObject.nodeName

获取特定节点类型的名�?
### msXmlNodeObject.nodeType

获取所需节点的类�?
节点类型

### msXmlNodeObject.nodeValue

设置或获取节点的文本�?
### msXmlNodeObject.parentNode

获取文档层次中的父对�?
### msXmlNodeObject.readyState

获取对象的当前状态�?
'uninitialized','loading','interactive','loaded' 'complete'

### msXmlNodeObject.removeChild(节点�?

移除节点

### msXmlNodeObject.replaceChild(新节�?旧节�?

替换节点

### msXmlNodeObject.selectNodes("字符串参�?)

查询节点

### msXmlNodeObject.selectNodes()

[返回对象:msXmlNodeObject](#msXmlNodeObject)

### msXmlNodeObject.selectSingleNode("字符串参�?)

查询节点

### msXmlNodeObject.selectSingleNode()

[返回对象:msXmlNodeObject](#msXmlNodeObject)

### msXmlNodeObject.setAttribute("属性名","属性�?)

修改属�?
也可以直接写 ele.属性名�?= �?
### msXmlNodeObject.setText()

修改文本属�?
### msXmlNodeObject.tagName

获取对象的标签名�?
### msXmlNodeObject.text

文本

### msXmlNodeObject.xml

xml源码

## msXmlNodeObject.childNodes 成员列表

子节点集�?
### msXmlNodeObject.childNodes.item()

[返回对象:msXmlNodeObject](#msXmlNodeObject)

## msxmlObject 成员列表

### msxmlObject.createNode()

[返回对象:msXmlNodeObject](#msXmlNodeObject)

### msxmlObject.createNode(类型,名称,名字空间)

创建节点

### msxmlObject.document

XML文档对象

[返回对象:msXmlDocObject](#msXmlDocObject)

### msxmlObject.documentElement

[返回对象:msXmlNodeObject](#msXmlNodeObject)

### msxmlObject.eachNode("tagName", )

```aardio aardio
//创建迭代�?遍历指定XML标记,例：
for i,xnode in msxmlObject.eachNode("tagName",/*可选指定父节点*/) {

}

```

### msxmlObject.eachNode()

```aardio aardio
//创建迭代�?遍历指定XML标记,例：
for i,xnode in msxmlObject.eachNode(/*可选指定tagName*/) {

}

[返回对象:msXmlNodeObject](#msXmlNodeObject)

```

### msxmlObject.getElementsByTagName("\*tagName")

根据标签名返回节�?
### msxmlObject.getElementsByTagName()

[返回对象:msXmlNodeObject](#msXmlNodeObject)

### msxmlObject.load(URL)

载入XML文档,参数可以是网址或本地路�?
### msxmlObject.loadXml()

从字符串载入XML文档,可选使用参�?指定内码

### msxmlObject.nodeFromId("字符串参�?)

根据ID返回节点

### msxmlObject.nodeFromId()

[返回对象:msXmlNodeObject](#msXmlNodeObject)

### msxmlObject.queryNodes

```aardio aardio
//可指定任意个属性条件�?支持模式匹配语法
msxmlObject.queryNodes( parent = 可选指定父节点;tagName = "标记")

```

### msxmlObject.queryNodes()

[返回对象:msXmlNodeObject](#msXmlNodeObject)

### msxmlObject.save("字符串参�?)

保存XML文档

### msxmlObject.selectNodes("字符串参�?)

查询节点�?
返回 COM 数组，使�?length 属性获取数组长度�?
返回数组起始索引�?0（aardio 普通数组起始索引为 1�?
### msxmlObject.setProperty("SelectionLanguage","XPath")

设置属�?
### msxmlObject.transformNode(XSL网址)

应用XSL样式

### msxmlObject.url

XML文件路径

### msxmlObject.xml

返回XML文本

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/web/msxml.md)

