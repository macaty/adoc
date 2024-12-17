[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# py3.module 库模块帮助文�?
## py3ModuleObject 成员列表

### py3ModuleObject.?

输入 Python 对象属性或函数名称�?
如果首字符为 $ ，则返回支持命名参数的函数对象�?
也就是说 pyObject.$fun 等价�?pyObject.fun.invoke�?
[返回对象:py3Object](object.html#py3Object)

### py3ModuleObject.getAttr("字符串参�?)

读属性值，也可以用成员操作符获取�?
除数值、布尔值、字符串、字节数组以外的值在 aardio 中存�?py.object 对象

### py3ModuleObject.getAttr()

[返回对象:py3Object](object.html#py3Object)

### py3ModuleObject.getDict()

如果对象是一个模�?返回字典对象

[返回对象:py3DictObject](#py3DictObject)

### py3ModuleObject.getFilename()

返回模块文件路径

### py3ModuleObject.getItem(索引)

返回指定索引的项，也可以用索引下标操作符 \[\] 取值�?
除数值、布尔值、字符串、字节数组以外的值在 aardio 中存�?py.object 对象

### py3ModuleObject.has("字符串参�?)

是否存在指定的属�?
### py3ModuleObject.setAttr("字符串参�?,)

写属性成员的值，也可以用成员操作符赋值�?
### py3ModuleObject.setItem(索引�?

修改指定索引的项，也可以用索引下标操作符 \[\] 赋值�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/py3/module.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/py3/module.md')

