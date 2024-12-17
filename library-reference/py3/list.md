[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# py3.list 库模块帮助文�?
## py3 成员列表

### py3.list

创建新的列表�?
此对象继承自pyObject（py3.object）�?
一般不需要手动创建此对象，aardio 会在传参数时自动转换

### py3.list()

[返回对象:py3ListObject](#py3ListObject)

### py3.list(aardio数组)

参数传入aardio数组,

创建并返回新的的python列表

注意 python中下标自0开�?而aardio中下标是�?开�?
### py3.list(pyObject对象)

如果传入 Python 对象是一�?list,

返回绑定相同对象�?py3.list 对象,添加引用计数,对象销毁时负责释放引用计数

否则将传入对象作�?python 内置函数 list 的参数并返回 py3.list 对象

失败返回 null

### py3.list(pyObject指针)

创建新的python列表,

不会添加引用计数,但对象销毁时负责释放引用计数

### py3.list(列表长度)

创建新的列表�?
也可以省略参�?
## py3ListObject 成员列表

### py3ListObject.?

[返回对象:py3Object](object.html#py3Object)

### py3ListObject.checkList()

检测是否列�?
### py3ListObject.each()

```aardio aardio
for( item in py3ListObject.each() ){
    /*创建迭代器用于遍历所有的�?返回一个�?/
}

[返回对象:py3Object](https://www.aardio.com/zh-cn/doc/library-reference/py3/object.html#py3Object)

```

### py3ListObject.getAttr("字符串参�?)

读属性值，也可以用成员操作符获取�?
除数值、布尔值、字符串、字节数组以外的值在 aardio 中存�?py.object 对象

### py3ListObject.getAttr()

[返回对象:py3Object](object.html#py3Object)

### py3ListObject.getItem()

[返回对象:py3Object](object.html#py3Object)

### py3ListObject.getItem(索引)

返回指定列表项，也可以用索引下标操作�?\[\] 取值�?
Python 列表起始下标�?0，可用负数索引表示从尾部计数�?
注意：普�?aardio 数组起始下标�?1，不能使用负数计�?
### py3ListObject.has("字符串参�?)

是否存在指定的属�?
### py3ListObject.parseValue()

转换�?aardio 数组�?
除浮点数�?3存储位以下整数、布尔值、字节数组之外的类型通过 JSON 转换�?aardio 值�?
转换�?aardio 数组�?
保留除浮点数�?3存储位以下整数、布尔值、字节数组之外的类型�?PyObject 不作转换�?
### py3ListObject.setAttr("字符串参�?,)

写属性成员的值，也可以用成员操作符赋值�?
### py3ListObject.setItem(索引�?

修改指定列表项，也可以用索引下标操作�?\[\] 赋值�?
Python 列表起始下标�?0，可用负数索引表示从尾部计数�?
注意：普�?aardio 数组起始下标�?1，不能使用负数计�?
### py3ListObject.stealPtr()

接管此对象的指针并盗用一次引用计�?
原对象的内部指针被清�?并不再负责释放引用计�?
steal references

### py3ListObject.toList()

转换�?Python 列表

[返回对象:py3ListObject](#py3ListObject)

### py3ListObject.toString()

转换�?aardio 字符�?
也可以直接将对象作为参数传入 tostring 函数转换为字符串

### py3ListObject.toTuple()

转换�?Python 元组

[返回对象:py3TupleObject](#py3TupleObject)

### py3ListObject.type()

返回类型名字

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/py3/list.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/py3/list.md')

