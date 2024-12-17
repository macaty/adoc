[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# py3.tuple 库模块帮助文�?
## py3 成员列表

### py3.tuple

元数组是只读的序列数�?数组元素不可变更

此对象继承自pyObject(py3.object)

一般不需要手动创建此对象,aardio会在传参数时自动转换

### py3.tuple()

[返回对象:py3TupleObject](#py3TupleObject)

### py3.tuple(aardio数组)

创建新的元数�?

如果数组成员中包�?pointer 类型指针,必须�?pyObject 指针,保持引用计数不变

### py3.tuple(pyObject对象)

如果传入 Python 对象是一�?tuple,

返回绑定相同对象�?py3.tuple 对象,添加引用计数,对象销毁时负责释放引用计数

否则将传入对象作�?python 内置函数 tuple 的参数并返回 py3.tuple 对象

失败返回 null

### py3.tuple(pyObject指针)

创建新的元数�?

不会添加引用计数,但对象销毁时负责释放引用计数

### py3.tuple(长度)

创建新的元数�?
## py3TupleObject 成员列表

### py3TupleObject.?

[返回对象:py3Object](object.html#py3Object)

### py3TupleObject.checkList()

检测是否列�?
### py3TupleObject.each()

```aardio aardio
for( item in py3TupleObject.each() ){
    /*创建迭代器用于遍历所有的�?返回一个�?/
}

[返回对象:py3Object](https://www.aardio.com/zh-cn/doc/library-reference/py3/object.html#py3Object)

```

### py3TupleObject.getAttr("字符串参�?)

读属性值，也可以用成员操作符获取�?
除数值、布尔值、字符串、字节数组以外的值在 aardio 中存�?py.object 对象

### py3TupleObject.getAttr()

[返回对象:py3Object](object.html#py3Object)

### py3TupleObject.getItem()

[返回对象:py3Object](object.html#py3Object)

### py3TupleObject.getItem(索引)

返回指定索引的项，也可以用索引下标操作符 \[\] 取值�?
除数值、布尔值、字符串、字节数组以外的值在 aardio 中存�?py.object 对象

### py3TupleObject.has("字符串参�?)

是否存在指定的属�?
### py3TupleObject.parseValue()

转换为aardio数组

### py3TupleObject.setAttr("字符串参�?,)

写属性成员的值，也可以用成员操作符赋值�?
### py3TupleObject.setItem(索引�?

修改指定索引的项，也可以用索引下标操作符 \[\] 赋值�?
### py3TupleObject.stealPtr()

接管此对象的指针并盗用一次引用计�?
原对象的内部指针被清�?并不再负责释放引用计�?
steal references

### py3TupleObject.toList()

转换�?Python 列表

[返回对象:py3ListObject](#py3ListObject)

### py3TupleObject.toString()

转换�?aardio 字符�?
也可以直接将对象作为参数传入 tostring 函数转换为字符串

### py3TupleObject.toTuple()

转换�?Python 元组

[返回对象:py3TupleObject](#py3TupleObject)

### py3TupleObject.type()

返回类型名字

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/py3/tuple.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/py3/tuple.md')

