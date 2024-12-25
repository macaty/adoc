[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# golang.slice 库模块帮助文�?
## golang 成员列表

### golang.slice()

创建 Go 切片�?
参数@1可用结构体指定原生数组，数组字段名必须为 value�?
Go 函数的参数类型必须声明为相同原生类型的数组指针�?
�?Go 调用返回以后，建议立即访�?value 字段获取 Go 返回的数组�?
因为 Go 的内存回收器稍后会回�?Go 数组的内存（至少在调用结束那一刻并不会立即回收）�?
转换以后此对象的内部指针即安全地指向 aardio 分配的内存�?
只要正确使用，go.slice 不会造成内存泄漏�?
如果不需要在 Go 中修改数组，�?value 字段总是指向 aardio 分配的内存�?
[返回对象:GoSliceObject](#GoSliceObject)

## GoSliceObject 成员列表

### GoSliceObject.value

返回或设置原生数组的�?
[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/golang/slice.md)

