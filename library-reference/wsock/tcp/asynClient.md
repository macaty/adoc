[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# wsock.tcp.asynClient 库模块帮助文�?
## tcpaclientObject 成员列表

### tcpaclientObject.\_form

用于处理套接字消息的窗口对象

[返回对象:winform](../../win/ui/_.html#winform)

### tcpaclientObject.asyncSelect(event)

检测到由event参数指明的网络事件后,

参数@1使用\_FD\_前缀的常量指�?可使用位或操作符指定多个选项

事件到达会触发相应的事件(参考on前缀的事件函�?,

失败返回null,以及错误信息,

成功返回true,以及上次调用此函数指定的event参数

### tcpaclientObject.bind

绑定 IP 端口�?
### tcpaclientObject.bind(IP,端口)

绑定 IP 端口�?
如果不指�?IP 则默认绑�?0.0.0.0�?
成功返回 true�?
失败返回 null,错误信息,错误代码�?
同一套接字重复绑定会返回 10022（\_WSAEINVAL�?错误�?
重新绑定应当重新创建套接字�?
这就好比一张车票只能上一次车�?
不能在已经上车以后再要求车站修改车票上的上车地�?
### tcpaclientObject.bufferSize

读写缓冲区大小，默认�?4KB

缓冲区如果设置的太小，会导致过于频繁的调用读写函�?
### tcpaclientObject.close()

关闭TCP客户端�?
如果未显式调用此函数，在对象析构时将会自动调用�?
已断开连接的套接字不能再使用，需要重连接请重新创建套接字�?
就好比用过的车票不能重复用，什么地方都有规则和限制�?
### tcpaclientObject.connect

创建连接�?
已关闭的套接字不能再使用，需要重连接请重新创建套接字�?
就好比用过的车票不能重复用，什么地方都有规则和限制�?
### tcpaclientObject.connect(IP或域�?端口�?

创建连接�?
也可以在参数 @1 中用一个字符串同时指定 IP 和端口号,IP 与端口号使用冒号分隔�?
异步套接字始终返�?null ，在 onOpen ,onError 回调事件中判断是否连接成功�?
### tcpaclientObject.eachRead

```aardio aardio
for(str,readSize,remainSize in tcpaclientObject.eachRead() ){
    /*可选指在eachRead参数中指定最大长�?
读取长度不可指定负数

迭代变量:
str是本迭代次读取的字符�?readSize是读取的长度,
remainSize是剩余还没有读取的字�?
如果限定了最大长�?remainSize�?时才表示读完所有数�?
此函数不支持unRead送回的数�?
异步客户端只能在onRead事件中使�?
如果套接字没有断开,并且出没有遇到错�?
但是还没有数据到�?此函数会等待数据
但不会阻塞消息循�?/
}

```

### tcpaclientObject.eachReadBuffer

```aardio aardio
for(readSize,remainSize in tcpaclientObject.eachReadBuffer() ){
    /*可选指在eachReadBuffer参数中指定最大长�?
读取长度不可指定负数

迭代变量:
readSize是本次迭代读取的长度,buffer的实际长度可能大于readSize,
remainSize是剩余还没有读取的字�?
如果限定了最大长�?remainSize�?时才表示读完所有数�?
此函数不支持unRead送回的数�?
异步客户端只能在onRead事件中使�?
如果套接字没有断开,并且出没有遇到错�?
但是还没有数据到�?此函数会等待数据
但不会阻塞消息循�?/
}

```

### tcpaclientObject.flush()

兼容aardio标准流接�?
### tcpaclientObject.getLocalIp()

返回连接的本地IP,端口�?
### tcpaclientObject.getRemoteIp()

返回连接的远程IP,端口�?
### tcpaclientObject.getSocketError()

获取并同时清除套接字错误代码

### tcpaclientObject.getopt(\_SO)

获取选项

参数@1使用\_SO\_前缀的常量指定选项,参数@2使用结构体指定�?
如果不指定参数@2,则获取一�?2位整型数�?

可选用参数@3指定设置层次，默认为SOL\_SOCKET

成功返回读取的结构体

### tcpaclientObject.hSocket

套接字句�?
关闭对象后为空�?
此值应由对象自动维护，调用者不应修改此属�?
### tcpaclientObject.isClosed()

套接字是否已关闭

### tcpaclientObject.isConnected()

套接字是否已连接

### tcpaclientObject.lastSelectEvent

最后一次调用asyncSelect应用的事�?
不可手动修改此属性，应由对象自动维护

### tcpaclientObject.lastSelectHwnd

最后一次调用asyncSelect应用的窗口句�?
不可手动修改此属性，应由对象自动维护

### tcpaclientObject.lastSelectMessageId

最后一次调用asyncSelect应用的消息ID

不可手动修改此属性，应由对象自动维护

### tcpaclientObject.onClose

```aardio aardio
tcpaclientObject.onClose = function(err){
    /*已断开连接,
如果缓冲区中仍然有数�?
这个事件可能在其他事件前面触�?/
}

```

### tcpaclientObject.onConnect

```aardio aardio
tcpaclientObject.onConnect = function(err){
    /*连接操作已完�?
连接成功时err�?，且readyState�?,
在这里可以开始发送数�?/
}

```

### tcpaclientObject.onOutOfBandData

```aardio aardio
tcpaclientObject.onOutOfBandData = function(err){
    /*收到紧急数�?
即send函数最后一个flag参数设为_MSG_OOB时发送的1字节带外数据*/
}

```

### tcpaclientObject.onRead

```aardio aardio
tcpaclientObject.onRead = function(err){
    /*收到数据,
可阻塞读取数�?
定义了此事件就不应同时定义onReceive事件*/
}

```

### tcpaclientObject.onReceive

```aardio aardio
tcpaclientObject.onReceive = function(err){
    /*收到数据,
仅读取已到达的数�?
定义了此事件就不应同时定义onRead事件*/
}

```

### tcpaclientObject.onSend

```aardio aardio
tcpaclientObject.onSend = function(err){
    /*发送数�?/
}

```

### tcpaclientObject.peek(长度)

读取但并不移除缓冲区的数�?返回字符�?
不指定参数则使用bufferSize指定的大小分配buffer并尝试读�?
### tcpaclientObject.read(读取长度)

读取数据

只能在onRead事件中使�?
参数可以指定长度,也可以使用接收数据的结构体作为参�?
此函数会循环读取数据�?
如果当前没有数据此函数会立即返回不会阻塞

如果读取长度指定为负�?此函数会等待数据到达直到读取全部数据

等待过程中不会阻塞消息循�?
不指定读取长度时表示读取一�?

使用CRLF回车换行符分�?
此函数如果读取部分不完整数据会调�?unRead 函数退回缓冲区

读取不到任何数据会调用shutdown函数关闭连接

### tcpaclientObject.readAll()

读取全部数据

只能在onRead事件中使�?
### tcpaclientObject.readAlloc

循环读取数据到动态指针内,

对于异步套接字，只能在onRead函数内使用此函数,

动态指针的使用风险较大,如果不是非常熟悉其规�?

建议不要使用此函�?
对象所有read前缀的成员函数底层基本都是调用这个函�?
此函数读取的数据支持调用unRead或unReadAlloc,

撤消并退回到读缓冲区

### tcpaclientObject.readAlloc()

循环读取数据，直到读取结�?

### tcpaclientObject.readAlloc(动态指�?

循环读取数据并存入参数指定的动态指�?

返回新的指针地址和内存长�?

此函数可能更新指针地址或分配的内存大小�?
必须使用返回的新指针覆盖原来保存该动态指针的变量�?
### tcpaclientObject.readAlloc(读取长度)

循环读取数据，直到达到参数中限定的最大长�?
无数据返回null�?
如果读取到数据则返回2个值：动态指�?内存长度

调用者必须负责调�?raw.realloc(0,动态指�?

释放返回�?返回的指�?
此函数直接操作内存，效率更好

但一定要记住释放返回的内存指�?
### tcpaclientObject.readBuffer(buffer,读取长度)

读取数据,返回 buffer 对象,

省略所有参数则读取所有数据，

参数@1可选指定一个使�?buffer 对象�?
省略读取长度时取缓冲区长度，

如果参数@1指定了缓冲区,成功返回读取长度,

否则成功返回缓冲区，

失败返回null

如果指定了长�?没有到完整的数据�?

此函数会将数据退回缓冲区,并返回null

如果读取出错,或没有读取到数据,此函数会自动调用shutdown关闭连接

### tcpaclientObject.readDelayInterval

数据尚未到达时的等待时间

此属性仅适用于界面线程异步套接字

仅在所有read前缀的读数据函数中，读取长度为负值是有效,

each前缀的迭代器函数也使用此属性指定的等待时间

### tcpaclientObject.readOobByte()

读取一个字节的紧急数�?返回字节�?
### tcpaclientObject.readTo

读取直到以指定的字符串结�?
只能在onRead事件中使�?
此函数如果读取部分不完整数据会调�?unRead() 退回缓冲区

读取不到任何数据会调用shutdown函数关闭连接

### tcpaclientObject.readTo('结束�?)

读取直到以指定的字符串结�?返回值不包含结束�?

该函数每次仅读取一个字�?效率较低

只能在onRead事件中使�?
### tcpaclientObject.readTo('结束�?,true)

读取直到以指定的字符串结�?返回值不包含结束�?

如果没有读取到数据，则循环等待，等待时继续处理界面消�?
此用法仅适用于界面线程异步套接字

该函数每次仅读取一个字�?效率较低

### tcpaclientObject.readyState

套接字连接状�?

0为等待连�?1为已连接,2为正在关�?3为已关闭

### tcpaclientObject.recv(最大接收长�?

单次接收数据�?
如果参数不指定长度，则使用bufferSize指定的长�?
成功返回字符�?

失败返回null,错误代码

recv,recvBuffer应在onReceive事件中使用，

在onReceive里不能多次调用recv,recvBuffer�?
recv,recvBuffer不保证每次一定会读完数据，所以在onClose事件里要继续读到没有任何数据�?
�?onRead事件中调用read前缀的系列函数可以循环读取所有接收的数据�?
这样就可以避免onClose以后还数据没有收完的问题

### tcpaclientObject.recvBuffer(缓冲�?读取长度)

单次接收数据�?
参数@1指定 buffer 对象,

参数@2可省�?默认为缓冲区长度,

成功返回接收的长�?

失败返回null,错误代码

recv,recvBuffer应在onReceive事件中使用，

在onReceive里不能多次调用recv,recvBuffer�?
recv,recvBuffer不保证每次一定会读完数据，所以在onClose事件里要继续读到没有任何数据�?
�?onRead事件中调用read前缀的系列函数可以循环读取所有接收的数据�?
这样就可以避免onClose以后还数据没有收完的问题

### tcpaclientObject.send(数据,长度)

单次发送数据包

### tcpaclientObject.setTimeouts(发送超�?接收超时)

设置超时,以亳秒为单位(1秒为1000毫秒)

### tcpaclientObject.setopt(\_SO)

设置选项

参数@1使用\_SO\_前缀的常量指定选项,参数@2使用结构体或数值指定�?
可选用参数@3指定设置层次，默认为SOL\_SOCKET

成功返回true

### tcpaclientObject.shutdown()

断开连接�?
参数中指�?0 为仅停止收数据，指定 1 为停止发送数据�?
默认值为 2 表示停止收发数据�?
此函数并不销毁套接字句柄，也不会关闭事件监听器�?
已断开连接的套接字不能再使用，需要重连接请重新创建套接字�?
就好比用过的车票不能重复用，什么地方都有规则和限制�?
### tcpaclientObject.unRead()

把read,readTo,readBuffer等函数读出的数据退回缓存，

注意退回数据的顺序是“后出先进”，

最后读出的应当最先退�?
### tcpaclientObject.unReadAlloc()

把readAlloc读取的动态指针退回缓�?

注意退回数据的顺序是“后出先进”，

最后读出的应当最先退�?
### tcpaclientObject.write(...)

发送数�?

支持一个或多个参数，参数支持字符串、buffer (buffer)、数值、结构体

成功返回true

### tcpaclientObject.writeBuffer(buffer,长度)

发送数�?

参数@1应使�?buffer 对象,

可选使用参�?指定长度

成功返回true

## wsock.tcp 成员列表

### wsock.tcp.asynClient

TCP异步客户�?
创建监听�?
### wsock.tcp.asynClient()

创建TCP异步客户�?
[返回对象:tcpaclientObject](asynClient.html#tcpaclientObject)

### wsock.tcp.asynClient(套接字句�?

绑定异步套接字返回客户端对象

不创建事件监听器

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/wsock/tcp/asynClient.md)

