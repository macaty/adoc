[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# py3.export 库模块帮助文�?
重要说明

## 一、简�?
�?py3.export() 作为对象构造函数使用时�?可用于导入参数指定的 aardio 对象�?Python 对象�?这种「代理对象」在 Python 中将保持对原�?aardio 对象的引用，也就是传址而非传值�?
## 二、解决了什么问�?
aardio 在与 Python 交互时，
默认除了布尔值、浮点数值、小�?3位的整数值，布尔值转换为�?aardio 值以外�?�?aardio 这些对象存为 pyObject，并保留对原�?Python 对象的引用�?
�?aardio 对象在自动转换为 Python 对象时，
默认是传值而非传址，Python 中不保留�?aardio 对象的引用�?
py3.export 的特别之处在于可以导�?aardio 模块�?Python�?�?Python 中引用与操作原始�?aardio 对象�?
例如�?
```
py3.export.aardio = {
    exportFunction = function(){

    }
}

```

然后可以�?Python �?import aardio，调用这个模块的所有成员函数�?
## 三、py3.export( aardioObject ) 使用要点

py3.export( aardioObject )
可以导出 aardio 中的 table,cdata,class,function �?aardio 对象�?也可以自动导�?aardio 迭代器，适用�?Python �?for 语句（aardio 迭代器在 Python 中返�?tuple 而非单个�?

对于整型数�?py3.export( number ) 默认转换�?Python 中的整型，而非浮点数�?其他类型（例如字符串�?py3.export 不作转换直接返回�?
Python 调用导出函数的返回值也会由 py3.export() 再次导出 �?Python 调用 aardio 导出函数的参数会自动调用 parseValue() 解析为纯 aardio 值�?
## 四、使用限�?
注意 py3.export 只能�?Python 启动线程中使�?
这是 Python 的限制与 aardio 无关�?
aardio 可以支持真多线程�?也提供了 py3.lock 简化了 Python 全局锁操作，支持�?py3.export 以外的接口�?但是：py3.export 不支持多线程�?
在非 Python 主线程下，py3.export �?null �?
使用 py3.mainThread 也可以检测是�?Python 主线程，

其实 Python 因为有全局�?—�?无法实现真正的多线程�?调用 process.python 创建多进程来替代多线程可能更方便一些�?
[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/py3/export.md)

