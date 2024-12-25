[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# fsys.localfile 库模块帮助文�?
## fsys 成员列表

### fsys.localfile

如果参数传入的不是硬盘文件路�?而是资源文件或内存数�?
则创建临时文件以获取本地路径

### fsys.localfile("/res/...")

创建资源文件路径本地化对�?

该对象用于保证资源文件返回的是本地路�?
路径会保持原来的文件�?
### fsys.localfile()

[返回对象:fsysLocalfileObject](#fsysLocalfileObject)

### fsys.localfile(内存数据,".默认后缀�?)

参数@1长度大于260字节,

则使用指定的后缀名生成临时文件保存该数据

## fsysLocalfileObject 成员列表

### fsysLocalfileObject.bindObject(对象)

绑定使用该文件的对象

### fsysLocalfileObject.free()

删除临时文件

### fsysLocalfileObject.loadDll()

[返回对象:dllModuleObject](../raw/_.html#dllModuleObject)

### fsysLocalfileObject.loadDll(调用约定)

加载 DLL

### fsysLocalfileObject.path()

本地化的完整路径

### fsysLocalfileObject.temp()

如果创建了临时文件则返回临时目录

如果该函数返回值为空则path为普通路�?
[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/fsys/localfile.md)

