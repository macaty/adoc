[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# wsock.tcp.asynServer 库模块帮助文�?
## tcpasynServerObject 成员列表

### tcpasynServerObject.\_beforeStop

```aardio aardio
tcpasynServerObject._beforeStop = function(){
    /*服务端关闭以前触�?此回调函数是标准库保留接�?用户不应使用此回�?/
}

```

### tcpasynServerObject.\_onClientClosed

```aardio aardio
tcpasynServerObject._onClientClosed = function(hSocket){
    /*客户端连接已经关闭时触发
此函数在连接断开后一定会被触�?此回调函数是标准库保留接�?用户不应使用此回�?/
}

```

### tcpasynServerObject.acceptCount

当前连接�?不可改动该�?
### tcpasynServerObject.beforeStop

```aardio aardio
tcpasynServerObject.beforeStop = function(){
    /*服务端关闭以前触�?/
}

```

### tcpasynServerObject.bind(IP,端口)

绑定 IP 与端口�?
应当�?start 函数自动调用此函数�?
### tcpasynServerObject.clearKeepAliveTimeout()

关闭所有超出keepAliveTimeout限制的超时连�?
在连接超出最大连接数�?此函数会被自动调�?
### tcpasynServerObject.client()

[返回对象:tcpaclientObject](asynClient.html#tcpaclientObject)

### tcpasynServerObject.client(hSocket)

用于获取客户端套接字对应的客户端对象

### tcpasynServerObject.clientBufferSize

客户端套接字读写缓冲区大小，默认�?MB

缓冲区如果设置的太小，会导致过于频繁的调用读写函�?
### tcpasynServerObject.getLocalIp()

返回当前绑定的IP,端口�?
### tcpasynServerObject.getRemoteIp(hSocket)

返回客户端IP地址,端口

### tcpasynServerObject.isClosed(hSocket)

连接是否已关�?
### tcpasynServerObject.isConnected(hSocket)

是否已连接并准备就绪

### tcpasynServerObject.keepAliveTimeout

最大保持连接时�?以秒为单�?

负数表示不限时间

### tcpasynServerObject.listen(请求队列大小)

监听构造函数绑定的 IP 端口，成功返�?true �?
已自动调用此函数�?
### tcpasynServerObject.maxConnection

最大连接数

### tcpasynServerObject.onClientClosed

```aardio aardio
tcpasynServerObject.onClientClosed = function(hSocket){
    /*客户端连接已经关闭时触发
此函数在连接断开后一定会被触�?/
}

```

### tcpasynServerObject.onClose

```aardio aardio
tcpasynServerObject.onClose = function(hSocket,err){
    var client = tcpasynServerObject.client(hSocket);

    /*已断开连接,
如果缓冲区中仍然有数�?
这个事件可能在其他事件前面触�?主动调用close函数立即关闭连接,此事件不会被触发,
但onClientClosed事件总会在关闭连接后触发*/
}

```

### tcpasynServerObject.onOpen

```aardio aardio
tcpasynServerObject.onOpen = function(hSocket,err){
    var client = tcpasynServerObject.client(hSocket);

    /*已连�?在这里可以开始发送数�?/
}

```

### tcpasynServerObject.onOutOfBandData

```aardio aardio
tcpasynServerObject.onOutOfBandData = function(hSocket,err){
    var client = tcpasynServerObject.client(hSocket);

    /*收到紧急数�?即send函数最后一个flag参数设为_MSG_OOB时发送的1字节带外数据*/
}

```

### tcpasynServerObject.onRead

```aardio aardio
tcpasynServerObject.onRead = function(hSocket,err){
    var client = tcpasynServerObject.client(hSocket);

    /*收到数据
可阻塞读取数�?定义了此事件就不应同时定义onReceive事件*/
}

```

### tcpasynServerObject.onReceive

```aardio aardio
tcpasynServerObject.onReceive = function(hSocket,err){
    var client = tcpasynServerObject.client(hSocket);

    /*收到数据
仅读取已到达的数�?定义了此事件就不应同时定义onRead事件*/
}

```

### tcpasynServerObject.onSend

```aardio aardio
tcpasynServerObject.onSend = function(hSocket,err){
    var client = tcpasynServerObject.client(hSocket);

    /*发送数�?/
}

```

### tcpasynServerObject.onStop

```aardio aardio
tcpasynServerObject.onStop = function(err){

    /*已停止服务端
主动调用stop函数停止服务端时不会触发此事�?/
}

```

### tcpasynServerObject.serverAddress

服务端监听地址

[返回对象:sockaddrInObject](#sockaddrInObject)

### tcpasynServerObject.shutdown()

断开 TCP 服务�?
### tcpasynServerObject.start(IP,端口,请求队列大小)

启动单线程异步TCP服务�?成功返回true,失败返回null,

如果不写IP，则默认设为"0.0.0.0"也即监听本机所有IP,访问此服务端也不限制IP

限制仅本机可以访问建议写127.0.0.1

端口�?或省略则自动查找1025以后的空闲端�?
注意0-1023为系统通用服务保留端口,

1024-49151为用户服务端�?其中大约%9已由IANA注册分配

49152-65535为私有或临时端口

### tcpasynServerObject.stop()

关闭 TCP 服务�?
## tcpasynServerObject.clients 成员列表

这是一个包含所有客户端套接字的表对�?
其中键为套接字句�?值为 wsock.tcp.asynClient对象

### tcpasynServerObject.clients.?

[返回对象:tcpaclientObject](asynClient.html#tcpaclientObject)

## wsock.tcp 成员列表

### wsock.tcp.asynServer()

创建单线程异步TCP服务�?
[返回对象:tcpasynServerObject](#tcpasynServerObject)

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/wsock/tcp/asynServer.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/wsock/tcp/asynServer.md')

