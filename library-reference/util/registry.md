[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# util.registry 库模块帮助文�?
## util 成员列表

### util.registry

引用注册�?用于注册对象唯一标识

### util.registry()

创建引用注册�?用于注册对象UID

[返回对象:utilRegistryObject](#utilRegistryObject)

## utilRegistryObject 成员列表

### utilRegistryObject.clear()

清空所有注册对�?
调用些函数时应确�?reg 函数之前注册的所�?id 已不再使�?

谨慎使用此函�?
### utilRegistryObject.reg(对象)

添加到注册表,返回唯一ID,

该ID可作为索引取回对�?
### utilRegistryObject.unReg(注册ID)

注销ID,并删除引�?

返回该ID之前引用的对�?
[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/util/registry.md)

