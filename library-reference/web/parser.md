[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# web.parser 库模块帮助文�?
## web 成员列表

### web.parser("HTML")

创建HTML简单解析器

如果要解析HTML全部节点请使用string.xml

### web.parser()

[返回对象:webParserObject](#webParserObject)

## web.parser 成员列表

HTML简单解�?
如果要解析HTML全部节点请使用string.xml

### web.parser.parseProperties(节点HTML)

提取HTML开始标记中的属性对

## webParserMetaObject 成员列表

### webParserMetaObject.equiv

所有指定EQUIV属性的content�?
键名一律小�?
### webParserMetaObject.name

所有指定NAME属性的content�?
键名一律小�?
## webParserObject 成员列表

### webParserObject.eachMeta()

```aardio aardio
for(meta in webParserObject.eachMeta() ){
    /*meta属性名一律小�?/
}

```

### webParserObject.getCharset()

获取页面编码,返回值一律小�?
### webParserObject.getDescription()

获取页面描述

### webParserObject.getKeywords()

获取页面描述

### webParserObject.getMetaContent(name)

获取页面META节点指定name值对应的content�?
name忽略大小�?
### webParserObject.getMetaTable()

返回META信息

[返回对象:webParserMetaObject](#webParserMetaObject)

### webParserObject.getTitle()

获取页面标题

### webParserObject.head

HEAD部分HTML

### webParserObject.isUtf8()

是否UTF-8编码

### webParserObject.local()

如果不是UTF8编码转换为UTF8,返回对象自身

[返回对象:webParserObject](#webParserObject)

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/web/parser.md)

