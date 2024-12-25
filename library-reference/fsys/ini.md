[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# fsys.ini 库模块帮助文�?
## fsys 成员列表

### fsys.ini

用于 ini 文件读写

fsys.ini 使用 UTF-8 编码读写 ini 文件�?
但操作系统自动转换为 ANSI 编码存储�?
如果不是为了兼容原来�?ANSI 程序，不必要使用 ini 文件格式�?
web.json, fsys.config 这些格式使用的都�?UTF-8 编码�?
使用也更方便�?
### fsys.ini("字符串参�?)

打开 ini 文件对象

### fsys.ini()

[返回对象:fsysiniObject](#fsysiniObject)

## fsysiniObject 成员列表

### fsysiniObject.eachSection()

[返回对象:inisectionObject](#inisectionObject)

```aardio aardio
for section in fsysiniObject.eachSection(/*可选用模式匹配搜索*/) {
    for(k,v in section){
        /*k为键,为�?section为当前遍历到的小�?/
    }
}

```

### fsysiniObject.getSection("字符串参�?)

读取或添加小节对�?可直接读写成�?
### fsysiniObject.getSection()

[返回对象:inisectionObject](#inisectionObject)

### fsysiniObject.getSectionNames()

获取所有小节名�?返回字符串数�?

### fsysiniObject.read("小节�?,"键名")

读取 ini 指字小节的指键键

可选使用参�?@3 指定默认�?
成功返回读取的�?失败返回 null

如果指定键名成功应返回字符串�?
不指定键名成功返回小节下所有键值组成的字符串数�?
返回字符串、数组、null 时都可以使用#操作符取长度,null 的长度为0�?
null,0 转换为逻辑值都等价�?false

### fsysiniObject.readKeys("小节�?)

返回指定小节中所有键名组成的字符串数�?
### fsysiniObject.readSectionNames()

返回小节名称组成的字符串数组

### fsysiniObject.write("小节�?,"键名","新�?)

�?ini 文件

健名�?null 删除指定的小�?
值为 null 删除指定的键�?
## inisectionObject 成员列表

### inisectionObject.?

可输入任意属性名,读写小节属�?

成功返回字符串�?失败返回null

### inisectionObject.name()

返回小节名称

### inisectionObject.save()

保存更改到ini文件

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/fsys/ini.md)

