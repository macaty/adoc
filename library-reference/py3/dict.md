[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# py3.dict 库模块帮助文�?
## py3 成员列表

### py3.dict

创建新的字典对象

此对象继承自 py3.object,

一般不需要手动创建此对象,aardio 会在传参数时自动转换

### py3.dict()

创建新字�?
[返回对象:py3DictObject](#py3DictObject)

### py3.dict(aardio�?

数为未指定元表的 aardio 表则转换�?Python 字典

### py3.dict(pyObject对象)

如果传入 Python 对象是一�?dict,

返回绑定相同对象�?py3.dict 对象,添加引用计数,对象销毁时负责释放引用计数

否则将传入对象作�?python 内置函数 dict 的参数并返回 py3.dict 对象

失败返回 null

### py3.dict(pyObject指针)

参数为指针则作为 Python 字典指针构建对象,

不会添加引用计数,但对象销毁时负责释放引用计数

## py3DictObject 成员列表

### py3DictObject.?

[返回对象:py3Object](object.html#py3Object)

### py3DictObject.checkDict()

检测是否字�?
### py3DictObject.each()

```aardio aardio
for( kObject,vObject in py3DictObject.each() ){
    /*两个都是py.object对象*/
}

[返回对象:py3Object](https://www.aardio.com/zh-cn/doc/library-reference/py3/object.html#py3Object)

```

### py3DictObject.eval("python表达�?,locals)

以该字典为名字空间运行代码并返回�?locals省略则默认为当前字典

类似python代码中的 execfile("test.py", globals, locals)

### py3DictObject.eval()

[返回对象:py3Object](object.html#py3Object)

### py3DictObject.exec("python代码",locals)

以该字典为名字空间运行代�?locals省略则默认为当前字典

类似python代码中的 exec "..." in globals, locals 语句

### py3DictObject.getAttr("字符串参�?)

读属性值，也可以用成员操作符获取�?
除数值、布尔值、字符串、字节数组以外的值在 aardio 中存�?py.object 对象

### py3DictObject.getAttr()

[返回对象:py3Object](object.html#py3Object)

### py3DictObject.getItem("键名")

返回指定索引的项，也可以用索引下标操作符 \[\] 取值�?
除数值、布尔值、字符串、字节数组以外的值在 aardio 中存�?py.object 对象

### py3DictObject.getItem()

[返回对象:py3Object](object.html#py3Object)

### py3DictObject.has("字符串参�?)

是否存在指定的属�?
### py3DictObject.parseValue()

转换�?aardio 表对�?
### py3DictObject.setAttr("字符串参�?,)

写属性成员的值，也可以用成员操作符赋值�?
### py3DictObject.setItem("键名",)

修改指定索引的项，也可以用索引下标操作符 \[\] 赋值�?
### py3DictObject.statement("python语句",locals)

以该字典为名字空间运行单个python语句

### py3DictObject.stealPtr()

接管此对象的指针并盗用一次引用计�?
原对象的内部指针被清�?并不再负责释放引用计�?
steal references

### py3DictObject.toList()

转换�?Python 列表

[返回对象:py3ListObject](#py3ListObject)

### py3DictObject.toString()

转换�?aardio 字符�?
也可以直接将对象作为参数传入 tostring 函数转换为字符串

### py3DictObject.toTuple()

转换�?Python 元组

[返回对象:py3TupleObject](#py3TupleObject)

### py3DictObject.type()

返回类型名字

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/py3/dict.md)

