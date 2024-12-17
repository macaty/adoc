[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# py3.object 库模块帮助文�?
## py3 成员列表

### py3.object

所有Python对象都是一个pyObject

在aardio中使用py3.object封装该指针为对象,

并自动管理引用计�?
### py3.object()

[返回对象:py3Object](object.html#py3Object)

### py3.object(aardio�?

将aardio值转换为pyObject

py3扩展库负责在与python交互时自动转换能转换的基础数据类型

其他对象aardio代码接触到的都会是py3.object

原始pyObject指针原则上保证不会返回给aardio调用代码

### py3.object(pyObject封装对象)

参数是py3.object封装对象

复制一个对象，并增加引用计�?
并负责在封装对象销毁时释放一次pyObject引用计数

这里传入的参数是aardio值，或者是py3.object统一都会返回py3.object

py3扩展库基于这种兼容性自动转换所有aardio,python对象

### py3.object(pyObject指针,true)

参数@2为true,参数@1就必须是pyObject对象指针

返回pyObject封装对象,并负责在封装对象销毁时释放一次pyObject引用计数,

原始pyObject指针原则上保证不会返回给aardio调用代码

这种用法仅用于py扩展库内部使�?
## py3Object 成员列表

### py3Object.?

输入 Python 对象属性或函数名称�?
如果首字符为 $ ，则返回支持命名参数的函数对象�?
也就是说 pyObject.$fun 等价�?pyObject.fun.invoke�?
[返回对象:py3Object](object.html#py3Object)

### py3Object.call()

[返回对象:py3Object](object.html#py3Object)

### py3Object.call(不定个数参数)

该对象为 Python 函数对象时支持使用此方法调用 Python 函数,

也可以不�?call 函数，直接作为普通函数调用�?
参数为不定个数的字符串、数值、布尔值等�?
如果函数调用成功�?
返回值除数值、布尔值、字符串、字节数组以外的�?
�?aardio 中存�?py.object 对象

### py3Object.callObject( py3.tuple对象 )

该对象为 Python 函数对象时支持使用此方法调用 Python 函数,

参数为tuple元数组对�?
返回值为 py3.object对象,可使�?tostring �?tonumber 等函数转换为aardio类型

### py3Object.callObject()

[返回对象:py3Object](object.html#py3Object)

### py3Object.checkBool()

检测是否布尔�?
### py3Object.checkBytes()

检测是否字节串

### py3Object.checkDict()

检测是否字�?
### py3Object.checkFloat()

检测是否浮点数

### py3Object.checkList()

检测是否列�?
### py3Object.checkLong()

检测是否整�?
### py3Object.checkNumber()

检测是否数�?
### py3Object.checkTuple()

检测是否字�?
### py3Object.checkUnicode()

检测是否字符串，注意Py3中字符串都是Unicode，取回aardio都是UTF8编码

### py3Object.each()

```aardio aardio
for( pyItem in py3Object.each() ){
    /*创建迭代器用于遍历所有的�?返回一个�?/
}

[返回对象:py3Object](https://www.aardio.com/zh-cn/doc/library-reference/py3/object.html#py3Object)

```

### py3Object.getAttr("字符串参�?)

读属性值，也可以用成员操作符获取�?
除数值、布尔值、字符串、字节数组以外的值在 aardio 中存�?py.object 对象�?
指定可选参�?@2 �?true 则不检查属性是否存在�?
### py3Object.getAttr()

[返回对象:py3Object](object.html#py3Object)

### py3Object.getFuncDesc

```aardio aardio
function(){
    return PyEval_GetFuncDesc(owner.pyObject );
}

```

### py3Object.getFuncDesc()

获取函数原型，返回值为字符串�?
### py3Object.getFuncName()

获取函数名，返回值为字符串�?
### py3Object.getFuncName（）

获取函数�?
### py3Object.getItem(索引)

返回指定索引的项，也可以用索引下标操作符 \[\] 取值�?
除数值、布尔值、字符串、字节数组以外的值在 aardio 中存�?py.object 对象

### py3Object.getTypeFlags()

返回类型特�?用法请参考此函数源码以及 Python 文档

### py3Object.has("字符串参�?)

是否存在指定的属�?
### py3Object.hasFeature()

检测类型特�?这个函数实现了C++中的PyType\_HasFeature宏相同的功能

### py3Object.invoke

该对象为 Python 函数对象时支持使用此方法调用 Python 函数,

与通过 call 方法调用不同的是 invoke 支持传递命名参数，

如果函数调用成功，返回值除数值、布尔值、字符串、字节数组以外的�?
�?aardio 中存�?py.object 对象�?
pyObject.func.invoke 可缩写为 pyObject.$func

### py3Object.invoke()

[返回对象:py3Object](object.html#py3Object)

### py3Object.invoke(kwarg=value,arg1...)

如果参数@1是未指定元表的纯表对�?且没�?pyObject 成员�?
则将该表中的名值对作为调用时的命名参数�?
该表中的数组成员作为调用时的匿名参数�?
注意名值对参数应当且只能写在最前面，所有参数请用逗号分隔�?
如果指定了第 2 个参数或更多参数，则 kwarg 的数组成员被忽略�?
如果参数 @1 不符合前述规则，

则与 call 调用相同的方式将所有参数作为调用时的匿名参数�?
如果参数 @1 �?null，则忽略第一个参数并禁用命名参数�?
并将第二个参数作为第一个参数，后续参数依次前移�?
### py3Object.invokeObject

该对象为 Python 函数对象时支持使用此方法调用 Python 函数,

与通过 call 方法调用不同的是 invokeObject 支持传递命名参数，

调用成功返回值为 py3.object 对象�?
invoke 函数调用 invokeObject 函数并会转换基础类型的值为�?aardio 值�?
### py3Object.invokeObject()

[返回对象:py3Object](object.html#py3Object)

[返回对象:py3Object](object.html#py3Object)

### py3Object.invokeObject(kwarg=value,arg1...)

如果参数@1是未指定元表的纯表对�?且没�?pyObject 成员�?
则将该表中的名值对作为调用时的命名参数�?
该表中的数组成员作为调用时的匿名参数�?
注意名值对参数应当且只能写在最前面，所有参数请用逗号分隔�?
如果指定了第 2 个参数或更多参数，则 kwarg 的数组成员被忽略�?
如果参数 @1 不符合前述规则，

则与 call 调用相同的方式将所有参数作为调用时的匿名参数�?
如果参数 @1 �?null，则忽略第一个参数并禁用命名参数�?
并将第二个参数作为第一个参数，后续参数依次前移�?
### py3Object.parseValue()

检�?Python 对象的类型，并自动返回对应的aardio类型对象�?
基础的数值字符串布尔值转换为同类型，整数值即使大�?53 位仍转为浮点数�?
dict, list, tuple 等等使用json格式转换�?aardio 类型的表

### py3Object.parseValue(true)

检测P ython 对象的类型，

基础类型返回对应�?aardio 类型对象，其他对象返回自身�?
基础类型指：数值、布尔值、字符串、字节数组�?
数值仅转换浮点数值，以及不大�?53位（bit）的整数值�?
字节数组�?Python 中的 bytes，aardio 中的 buffer 对象�?
所�?Python 返回的对象自动调用此函数转换基础类型�?
### py3Object.setAttr("字符串参�?,)

写属性成员的值，也可以用成员操作符赋值�?
### py3Object.setItem(索引�?

修改指定索引的项，也可以用索引下标操作符 \[\] 赋值�?
### py3Object.size64()

获取64位无符号长整�?
返回 math.size64 对象

### py3Object.stealPtr()

接管此对象的指针并盗用一次引用计�?
原对象的内部指针被清�?并不再负责释放引用计�?
steal references

### py3Object.toBool()

解析�?aardio 布尔�?
### py3Object.toBytes()

解析�?aardio 字节数组

### py3Object.toDict()

如果 Python 对象是一�?dict,

返回绑定相同 Python 对象�?py3.dict 对象,

添加引用计数,对象销毁时负责释放引用计数,

否则将传入对象作�?Python 内置函数 dict 的参数并返回 py3.dict 对象,

失败返回null

[返回对象:py3DictObject](#py3DictObject)

### py3Object.toList()

如果 Python 对象是一�?list,

返回绑定相同 Python 对象�?py3.list 对象,

添加引用计数,对象销毁时负责释放引用计数,

否则将传入对象作�?Python 内置函数 list 的参数并返回 py3.list 对象,

失败返回null

[返回对象:py3ListObject](#py3ListObject)

### py3Object.toNumber()

解析�?aardio 数�?
也可以直接将对象传入 tonumber 函数并转换为数�?
### py3Object.toStr()

Python 对象转换�?Python 字符串对�?

相当于调�?Python 中的 str 函数,

如果要返�?aardio 字符串可使用 toString 函数,

也可以调�?py3.str 函数创建 Python 字符串对�?
### py3Object.toString()

Python 对象转换�?aardio 字符�?
Python 字节数组（bytes）解析为aardio中的字节数组（buffer�?
其他类型尝试调用 Python 中的 str 函数转换�?aardio 字符�?

也可以直接将对象作为参数传入 tostring 函数转换为字符串

### py3Object.toTuple()

如果 Python 对象是一�?tuple,

返回绑定相同 Python 对象�?py3.tuple 对象,

添加引用计数,对象销毁时负责释放引用计数,

否则将传入对象作�?Python 内置函数 tuple 的参数并返回 py3.tuple 对象,

失败返回null

[返回对象:py3TupleObject](#py3TupleObject)

### py3Object.type()

返回类型名字

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/py3/object.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/py3/object.md')

