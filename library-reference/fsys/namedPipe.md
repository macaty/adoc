[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# fsys.namedPipe 库模块帮助文�?
## fsys 成员列表

### fsys.namedPipe("\\.\\pipe\\pipename",2,2000)

参数分别为管道名,最大实例数,超时�?
其他参数就参考源�?
### fsys.namedPipe()

[返回对象:fsysPipeObject](#fsysPipeObject)

## fsys.namedPipe 成员列表

### fsys.namedPipe.wait("\\.\\pipe\\pipename","r+")

等待并打开可用管道

### fsys.namedPipe.wait()

[返回对象:fsysPipeObject](#fsysPipeObject)

## fsysPipeObject 成员列表

### fsysPipeObject.close()

关闭文件句柄

### fsysPipeObject.connect()

等待客户端连�?
### fsysPipeObject.disconnect()

断开客户端连�?
### fsysPipeObject.flush()

刷新缓冲�?
### fsysPipeObject.getClientComputerName()

返回客户端计算机名，不支持WinXP系统

### fsysPipeObject.getClientProcessId()

返回客户端进程ID

### fsysPipeObject.getClientSessionId()

返回客户端会话ID

### fsysPipeObject.handle

返回文件句柄

### fsysPipeObject.path

返回文件路径

### fsysPipeObject.peek()

如果命名管道中有数据则返回数�?
### fsysPipeObject.read()

读取一行文�?
返回文本不包含回车换行符

### fsysPipeObject.read(-1)

读取所有内容到文件尾部

### fsysPipeObject.read({int number} )

参数可以是一个结构体

不支持多参数

### fsysPipeObject.read(字节�?

读取指定长度的字�?
不支持多参数

### fsysPipeObject.readBuffer

读取数据�?buffer ,成功返回读取长度,失败返回null

### fsysPipeObject.readBuffer(buffer,读取长度)

直接读数据到内存

参数@1可以�?buffer 对象,或内存指�?

如果是指针则必须指定读取长度,否则长度参数可�?
成功返回读取长度

### fsysPipeObject.seek("cur",)

移动至相对当前位置的指定偏移�?
### fsysPipeObject.seek("end")

移动指针至结束处

返回当前位置,返回值大�?GB则为负�?

获取文件大小推荐使用 size() 函数

### fsysPipeObject.seek("end",)

移动至相对结束处的指定偏移量

### fsysPipeObject.seek("set")

移动指针到开�?
### fsysPipeObject.seek("set",)

移动至相对开始处的指定偏移量

### fsysPipeObject.seek()

得到当前位置

### fsysPipeObject.seteof()

设置文件结束

### fsysPipeObject.size()

返回文件大小

可选参数一指定单位大小(默认自动选择),

可选用参数二指定小数精�?默认�?)

返回文件大小,单位大小,单位�?"bytes","KB","MB","GB"�?

### fsysPipeObject.size64()

返回文件大小

返回值为math.size64长整数对�?
[返回对象:mathSize64Object](../math/_.html#mathSize64Object)

### fsysPipeObject.write(字符�?

写入字符�?
参数也可以是数值、结构体

### fsysPipeObject.writeBuffer

写入缓冲区数�?成功返回写入长度,失败返回null

### fsysPipeObject.writeBuffer(buffer,写入长度)

直接写数据到内存

参数@1可以�?buffer 对象,或内存指�?

如果是指针则必须指定写入长度,否则长度参数可�?
成功返回写入长度

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/fsys/namedPipe.md)

