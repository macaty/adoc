[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# fsys.stream 库模块帮助文�?
## fsys 成员列表

### fsys.stream

文件流对�?
兼容IStream,ISequentialStream接口

创建文件流对�?返回对象可传入其他线程使用�?
### fsys.stream("文件路径","a")

只写追加模式打开文件�?创建新文件保留原文件

### fsys.stream("文件路径","a+")

读写追加模式打开文件�?创建新文件保留原文件

注意流对象总是以二进制模式读写，不需要添加b标记

### fsys.stream("文件路径","r+")

读写模式打开文件�?文件必须存在

注意流对象总是以二进制模式读写，不需要添加b标记

### fsys.stream("文件路径","w")

只写模式打开文件�?创建新文件清空原文件

注意流对象总是以二进制模式读写，不需要添加b标记

### fsys.stream("文件路径","w+")

读写模式打开文件�?创建新文件清空原文件

注意流对象总是以二进制模式读写，不需要添加b标记

### fsys.stream()

[返回对象:fsysStreamObject](stream.html#fsysStreamObject)

### fsys.stream(IStream接口指针)

直接使用指针创建对象

### fsys.stream(IStream接口指针,true)

直接使用指针创建对象,该指针的COM引用计数减一

注意对象自身会增加COM引用计数并在释放时移�?
### fsys.stream(初始化数�?缓冲区长�?

创建内存流文�?所有参数可�?
可选使用参数@3指定选项,此参数请参考库源码

## fsysStreamObject 成员列表

### fsysStreamObject.close()

关闭对象

### fsysStreamObject.commit(flags)

提交更改

### fsysStreamObject.flush()

提交更改

兼容aardio标准流接�?
### fsysStreamObject.lockPointer()

如果这是一个内存流,

锁定内存并返回内存指针，内存长度,

需要使用对象的unlockPointer()成员函数解锁内存

写入内存流可能导致重新分配内�?所以返回的指针可能会变�?
### fsysStreamObject.read

读数�?
### fsysStreamObject.read(-1)

参数指定读取长度,-1为读到尾�?
参数也可以指定一个结构体用于填充读取的数�?

无参数读取一�?
### fsysStreamObject.read(0)

是否未到达文件尾�?
如果已经到达文件尾返�?null，否则返回空字符串�?
注意在布尔表达式�?null 等于 false，空字符串等�?true�?
### fsysStreamObject.readAll()

移到指针到文件头

读取到文件尾返回所有数�?
### fsysStreamObject.readBuffer(buffer,读取长度)

读取数据�?buffer,

参数@1应是 buffer 对象或指针，

参数@2省略则默认为缓冲区长度�?
成功返回读取长度

### fsysStreamObject.readTo

读取直到以指定的字符串结�?
### fsysStreamObject.readTo('结束�?)

读取直到以指定的字符串结�?返回值不包含结束�?

该函数每次仅读取一个字�?效率较低

### fsysStreamObject.reset()

文件指针移动到开�?
类似seek(0,"set"),不同的是此函数返回对象自�?
[返回对象:fsysStreamObject](stream.html#fsysStreamObject)

### fsysStreamObject.revert()

撤消更改

### fsysStreamObject.seek("cur",)

移动至相对当前位置的指定偏移�?
### fsysStreamObject.seek("end")

移动指针至结束处

### fsysStreamObject.seek("end",)

移动至相对结束处的指定偏移量

### fsysStreamObject.seek("set")

移动指针到开�?
### fsysStreamObject.seek("set",)

移动至相对开始处的指定偏移量

### fsysStreamObject.seek()

得到当前位置

### fsysStreamObject.size()

得到数据长度

### fsysStreamObject.stat()

返回流状�?
返回值为STATSTG结构�?
[返回对象:fsysstramSTATSTGObject](#fsysstramSTATSTGObject)

### fsysStreamObject.unlockPointer()

解锁内存

用lockPointer函数获取内存指针使用以后，必须调用此函数

### fsysStreamObject.write

写数�?
### fsysStreamObject.write(数据,长度)

写入数据

参数@1可使用字符串、buffer、指针、结构体�?
如果指定指针就必须明确指定写入长�?
### fsysStreamObject.writeBuffer(buffer,读取长度)

buffer 写入�?

参数@1应是 buffer 对象或指针，

参数@2省略则默认为缓冲区长�?
## fsysstramSTATSTGObject 成员列表

### fsysstramSTATSTGObject.cbSize

文件长度

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/fsys/stream.md)

