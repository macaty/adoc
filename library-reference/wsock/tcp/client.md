[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# wsock.tcp.client 库模块帮助文�?
## wsock.tcp.client 成员列表

TCP客户端支持库

### wsock.tcp.client.getLocalIp

获取上网�?IP

### wsock.tcp.client.getLocalIp(主机,端口,超时秒数)

获取上网�?IP，所有参数可省略�?
如果指定目标主机与端口，则优先返回访问目标主机的网卡 IP�?
主机可指定域名或 IP，建议指定稳定的主机�?
端口省略则默认为 80，省略超时参数则默认�?0.3 �?
### wsock.tcp.client.test

检测目标主机是否可建立 TCP 连接

如果已连接网络则返回建立链接的网�?IP，否则返�?null

### wsock.tcp.client.test(主机,端口,超时秒数)

检测目标主机是否可建立 TCP 连接，所有参数可省略�?
主机可指定域名或 IP，也可以指定包含多个主机的数组，

端口省略则默认为 80，省略超时参数则默认�?0.3 �?
如果可以连接任一指定的目标主机则返回建立连接的网�?IP�?
否则返回 null

## tcpclientObject 成员列表

### tcpclientObject.\_onClosed

```aardio aardio
tcpclientObject._onClosed = function(){
    /*套接字关闭以前触�?此回调函数是标准库保留接�?用户不应使用此回�?/
}

```

### tcpclientObject.asyncSelect(event,userMsgId,hwnd)

检测到由event参数指明的网络事件后,

参数@1使用\_FD\_前缀的常量指�?可使用位或操作符指定多个选项

事件到达向hwnd指定句柄的窗口发送userMsgId消息,

第二次调用此函数可省略句柄以及消息ID

失败返回null,以及错误信息,

成功返回true,以及上次调用此函数指定的event参数

### tcpclientObject.bind

绑定 IP 端口�?
### tcpclientObject.bind(IP,端口)

绑定 IP 端口�?
如果不指�?IP 则默认绑�?0.0.0.0�?
成功返回 true�?
失败返回 null,错误信息,错误代码�?
同一套接字重复绑定会返回 10022（\_WSAEINVAL�?错误�?
重新绑定应当重新创建套接字�?
这就好比一张车票只能上一次车�?
不能在已经上车以后再要求车站修改车票上的上车地�?
### tcpclientObject.bufferSize

读写缓冲区大小，默认�?1MB

缓冲区如果设置的太小，会导致过于频繁的调用读写函�?
### tcpclientObject.close()

关闭并释�?TCP 客户端�?
如果关闭了套接字此函数返�?true

如果套接字已经关闭，此函数返�?null�?
如果未显式调用此函数�?
在对象析构时,将会自动调用�?
已关闭的套接字不能再使用，需要重连接请重新创建套接字�?
就好比用过的车票不能重复用，什么地方都有规则和限制�?
### tcpclientObject.connect

创建连接�?
已关闭的套接字不能再使用，需要重连接请重新创建套接字�?
就好比用过的车票不能重复用，什么地方都有规则和限制�?
### tcpclientObject.connect(IP或域�?端口�?

创建连接，成功返�?true�?
也可以在参数 @1 中用一个字符串同时指定 IP 和端口号,IP 与端口号使用冒号分隔�?
失败返回 null ，错误信�?
异步套接字始终返�?null ，在 onOpen ,onError 回调事件中判断是否连接成�?
### tcpclientObject.connectTimeout

创建连接，可指定超时�?
已关闭的套接字不能再使用，需要重连接请重新创建套接字�?
就好比用过的车票不能重复用，什么地方都有规则和限制�?
### tcpclientObject.connectTimeout(IP或域�?端口�?超时秒数)

创建连接，成功返�?true�?
也可以在参数 @1 中用一个字符串同时指定 IP 和端口号,IP 与端口号使用冒号分隔�?
注意：超时是以秒为单位，不是毫秒！！

省略超时参数则默认值为 0.5 秒�?
### tcpclientObject.eachRead

```aardio aardio
for(str,readSize,remainSize in tcpclientObject.eachRead() ){
    /*可选指在eachRead参数中指定最大长�?
str是本次读取的字符�?readSize是读取的长度,
remainSize是剩余还没有读取的字�?
如果限定了最大长�?remainSize�?时才表示读完所有数�?
此函数不支持unRead送回的数�?也不适合于异步套接字*/
}

```

### tcpclientObject.eachReadBuffer

```aardio aardio
for(readSize,remainSize in tcpclientObject.eachReadBuffer() ){
    /*可选指在eachReadBuffer参数中指定最大长�?
readSize是读取的长度,buffer的实际长度可能大于readSize,
remainSize是剩余还没有读取的字�?
如果限定了最大长�?remainSize�?时才表示读完所有数�?此函数不支持unRead送回的数�?也不适合于异步套接字*/
}

```

### tcpclientObject.flush()

兼容aardio标准流接�?
### tcpclientObject.getLocalIp()

返回连接的本地IP,端口�?
### tcpclientObject.getRemoteIp()

返回连接的远程IP,端口�?
### tcpclientObject.getSocketError()

获取并同时清除套接字错误代码

### tcpclientObject.getopt(\_SO)

获取选项

参数@1使用\_SO\_前缀的常量指定选项,参数@2使用结构体指定�?
如果不指定参数@2,则获取一�?2位整型数�?

可选用参数@3指定设置层次，默认为SOL\_SOCKET

成功返回读取的结构体

### tcpclientObject.hSocket

套接字句柄�?
关闭对象后为空值�?
此值应由对象自动维护，调用者不应修改此属�?
### tcpclientObject.isClosed()

套接字是否已关闭

### tcpclientObject.isConnected()

套接字是否已连接

### tcpclientObject.lastSelectEvent

最后一次调用asyncSelect应用的事�?
不可手动修改此属性，应由对象自动维护

### tcpclientObject.lastSelectHwnd

最后一次调用asyncSelect应用的窗口句�?
不可手动修改此属性，应由对象自动维护

### tcpclientObject.lastSelectMessageId

最后一次调用asyncSelect应用的消息ID

不可手动修改此属性，应由对象自动维护

### tcpclientObject.onClosed

```aardio aardio
tcpclientObject.onClosed = function(){
    /*套接字关闭以前触�?/
}

```

### tcpclientObject.peek(长度)

读取但并不移除缓冲区的数�?返回字符�?
不指定参数则使用bufferSize指定的大小分配buffer并尝试读�?
### tcpclientObject.read

读取数据

此函数等待数据到�?

但如果参数未省略且不�?1,则不保证读取达到定的长度

如果要等待直到指定长度应改用 readEx 函数

### tcpclientObject.read(读取长度)

读取数据

参数可以指定长度,也可以使用接收数据的结构体作为参�?
参数�?1表示读到尾部,无参数表示读取一�?

使用CRLF回车换行符分�?
此函数等待数据到�?

但如果参数未省略且不�?1,则不保证读取达到定的长度

### tcpclientObject.readAll()

接收全部数据

该函数读取直至连接关�?应慎用该函数防止服务器保持连接无法返�?
### tcpclientObject.readAlloc

循环读取数据到动态指针内,

动态指针的使用风险较大,如果不是非常熟悉其规�?

建议不要使用此函�?
对象所有read前缀的成员函数底层基本都是调用这个函�?
此函数读取的数据支持调用unRead或unReadAlloc,

撤消并退回到读缓冲区

### tcpclientObject.readAlloc()

循环读取数据，直到读取结�?

### tcpclientObject.readAlloc(动态指�?

循环读取数据并存入参数指定的动态指�?

返回新的指针地址和内存长�?

此函数可能更新指针地址或分配的内存大小�?
必须使用返回的新指针覆盖原来保存该动态指针的变量�?
### tcpclientObject.readAlloc(读取长度)

循环读取数据，直到达到参数中限定的最大长�?
读取长度不可指定负数,负数仅用于界面线程异步套接字

无数据返回null�?
如果读取到数据则返回2个值：动态指�?内存长度

调用者必须负责调�?raw.realloc(0,动态指�?

释放返回�?返回的指�?
此函数直接操作内存，效率更好

但一定要记住释放返回的内存指�?
### tcpclientObject.readAllocEx(读取长度)

读取数据达到指定长度,参数不可省略

成功返回动态指�?数据长度,

动态指针必须用 raw.realloc 函数释放,

非必要请不要直接使用此函�?应改�?readEx 函数

此函数不可用于异步套接字

### tcpclientObject.readBuffer(缓冲�?读取长度)

读取数据,返回 buffer 对象,

省略所有参数则读取所有数据，

参数@1可选指定一个使�?buffer 对象�?
省略读取长度时取缓冲区长度，

如果参数@1指定了缓冲区,成功返回读取长度,

否则成功返回缓冲区，

失败返回null

### tcpclientObject.readDelayInterval

数据尚未到达时的等待时间

此属性仅适用于界面线程异步套接字

仅在读取长度为负值是有效

### tcpclientObject.readEx(读取长度)

读取数据达到指定长度,参数不可省略

成功返回字符�?如果套接字关�?则返回已读取的数�?
此函数不可用于异步套接字

### tcpclientObject.readOobByte()

读取一个字节的紧急数�?返回字节�?
### tcpclientObject.readTo

读取直到以指定的字符串结�?
如果只是读取部分数据并没有获取到结束标记，第二个返回值为true

否则只会返回一个�?成功返回读取字符�?

失败返回null

### tcpclientObject.readTo('结束�?)

读取直到以指定的字符串结�?返回值不包含结束�?

该函数每次仅读取一个字�?效率较低

### tcpclientObject.readTo('结束�?,true)

读取直到以指定的字符串结�?返回值不包含结束�?

如果没有读取到数据，则循环等待，等待时继续处理界面消�?
此用法仅适用于界面线程异步套接字

该函数每次仅读取一个字�?效率较低

### tcpclientObject.readyState

套接字连接状�?

0 为等待连�?1 为已连接,2 为正在关�?3 为已关闭

### tcpclientObject.recv(最大接收长�?

单次接收数据�?
如果参数不指定长度，则使用bufferSize指定的长�?
成功返回字符�?

失败返回null,错误代码

### tcpclientObject.recvBuffer(缓冲�?读取长度)

单次接收数据�?
参数@1指定 buffer 对象,

参数@2可省�?默认为缓冲区长度,

成功返回接收的长�?

失败返回null,错误代码

### tcpclientObject.reuseAddress(true)

是否允许端口重用

### tcpclientObject.send(数据,长度)

单次发送数据包

成功返回发送的数据长度,

失败返回null,错误代码

### tcpclientObject.sendbuffer10035

异步套接字发送缓冲区,用户不应修改此对�?
### tcpclientObject.setTimeouts(发送超�?接收超时)

设置超时,以亳秒为单位(1秒为1000毫秒)

### tcpclientObject.setopt(\_SO)

设置选项

参数@1使用\_SO\_前缀的常量指定选项,参数@2使用结构体、数值、布尔值都可以

可选用参数@3指定设置层次，默认为SOL\_SOCKET

成功返回true

### tcpclientObject.shutdown()

断开连接�?
参数中指�?0 为仅停止收数据，指定 1 为停止发数据�?
默认值为 2 表示停止收发送数据�?
此函数并不销毁套接字句柄�?
已断开连接的套接字不能再使用，需要重连接请重新创建套接字�?
就好比用过的车票不能重复用，什么地方都有规则和限制�?
### tcpclientObject.unRead()

把read,readTo,readBuffer等函数读出的数据退回缓存，

注意退回数据的顺序是“后出先进”，

最后读出的应当最先退�?
### tcpclientObject.unReadAlloc()

把readAlloc读取的动态指针退回缓�?

注意退回数据的顺序是“后出先进”，

最后读出的应当最先退�?
### tcpclientObject.write(...)

发送数�?

支持一个或多个参数，参数支持字符串、buffer (buffer)、数值、结构体

成功返回true

### tcpclientObject.writeBuffer(缓冲�?长度)

发送数�?

参数@1应使�?buffer 对象,

可选使用参�?指定长度

成功返回true

## wsock.tcp 成员列表

### wsock.tcp.client()

[返回对象:tcpclientObject](client.html#tcpclientObject)

### wsock.tcp.client(套接字句�?

绑定套接字句柄并返回TCP客户端对�?
### wsock.tcp.client(缓冲区大�?套接字句�?

创建 TCP 客户�?

套接字为空则创建套接�?否则绑定套接字句�?

缓冲区大小为可选参�?默认�?KB

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/wsock/tcp/client.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/wsock/tcp/client.md')

