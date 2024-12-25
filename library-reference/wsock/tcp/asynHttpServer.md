[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# wsock.tcp.asynHttpServer 库模块帮助文�?
## asynHttpServerObject 成员列表

### asynHttpServerObject.\_beforeHttpServerStop

```aardio aardio
asynHttpServerObject._beforeHttpServerStop = function(){
    /*服务端关闭以前触�?此回调函数是标准库保留接�?用户不应使用此回�?/
}

```

### asynHttpServerObject.\_onClientClosed

```aardio aardio
asynHttpServerObject._onClientClosed = function(hSocket){
    /*客户端连接已经关闭时触发
此函数在连接断开后一定会被触�?此回调函数是标准库保留接�?用户不应使用此回�?/
}

```

### asynHttpServerObject.acceptCount

当前连接�?不可改动该�?
### asynHttpServerObject.beforeStop

```aardio aardio
asynHttpServerObject.beforeStop = function(){
    /*服务端关闭以前触�?/
}

```

### asynHttpServerObject.bind(IP,端口)

绑定 IP 与端口�?
应当�?start 函数自动调用此函数�?
### asynHttpServerObject.clearKeepAliveTimeout()

关闭所有超出keepAliveTimeout限制的超时连�?
在连接超出最大连接数�?此函数会被自动调�?
### asynHttpServerObject.client()

[返回对象:tcpaclientObject](asynClient.html#tcpaclientObject)

### asynHttpServerObject.client(hSocket)

用于获取客户端套接字对应的客户端对象

### asynHttpServerObject.clientBufferSize

客户端套接字读写缓冲区大小，默认�?MB

缓冲区如果设置的太小，会导致过于频繁的调用读写函�?
### asynHttpServerObject.customErrors

```aardio aardio
asynHttpServerObject.customErrors = {
    [404] = function(response){
        response.status = "404 Not Found";
        response.write("404 Not Found"); /*自定义错误页�?也可以直接指定错误页路径*/
    }
}

```

### asynHttpServerObject.defalutDocument

默认文档，默认为"main.aardio",

如果访问硬盘上存在的目录,request.path 尾部不加斜杠会自动跳转到以斜杆结束的路径

如果访问嵌入资源目录,只有 request.path 以斜杆才会访问默认文�?

对于访问嵌入资源文件,建议指定完整的文件路�?

默认文档主要是用于硬盘上的网�?
### asynHttpServerObject.defaultUrl

访问此服务器的默认网址

### asynHttpServerObject.documentBase

网站根目�?

不会修改应用程序根目�?支持硬盘目录与资源目�?

这个属性应当设置为应用程序根目录下的相对路�?

例如 "/res/web/"

注意�?request.path 前面包含 documentBase 目录�?
�?request.pathInfo 忽略 documentBase 目录

### asynHttpServerObject.documentRoot

网站应用程序根目�?默认�?/",

只能设置为硬盘上实际存在的目�?

改变此目�?会同时改�?
服务端代码中的应用程序根目录以及用户库目�?

如果只是相将所有请求路径转向某个目�?应当改用 documentBase 属�?
如果网站在嵌入资源目录中,应当改用 documentBase 属�?
### asynHttpServerObject.getLocalIp()

返回当前绑定的IP,端口�?
### asynHttpServerObject.getRemoteIp(hSocket)

返回客户端IP地址,端口

### asynHttpServerObject.getUrl

返回 HTTP 服务端访问网址

如果服务器启动失败不返回任何�?
### asynHttpServerObject.getUrl()

返回首页网址

### asynHttpServerObject.getUrl(path,localIp)

返回 @path 指定路径的网址，路径开始可省略斜杠�?
注意参数第一个字符不需要指定斜�?
可选用 @localIp 指定 IP "0.0.0.0" 是否替换为上网卡 IP（否�?localhost �?
### asynHttpServerObject.getUrl(path,param,localIp)

返回 @path 指定路径的网址，路径开始可省略斜杠�?
@param 指定 URL 参数表（table 对象）�?
可选用 @localIp 指定 IP "0.0.0.0" 是否替换为上网卡 IP（否�?localhost �?
### asynHttpServerObject.isClosed(hSocket)

连接是否已关�?
### asynHttpServerObject.isConnected(hSocket)

是否已连接并准备就绪

### asynHttpServerObject.keepAliveTimeout

最大保持连接时�?以秒为单�?

负数表示不限时间

### asynHttpServerObject.listen(请求队列大小)

监听构造函数绑定的 IP 端口，成功返�?true �?
已自动调用此函数�?
### asynHttpServerObject.maxConnection

最大连接数

### asynHttpServerObject.onClientClosed

```aardio aardio
asynHttpServerObject.onClientClosed = function(hSocket){
    /*客户端连接已经关闭时触发
此函数在连接断开后一定会被触�?/
}

```

### asynHttpServerObject.onClose

```aardio aardio
asynHttpServerObject.onClose = function(hSocket,err){
    var client = asynHttpServerObject.client(hSocket);

    /*已断开连接,
如果缓冲区中仍然有数�?
这个事件可能在其他事件前面触�?主动调用close函数立即关闭连接,此事件不会被触发,
但onClientClosed事件总会在关闭连接后触发*/
}

```

### asynHttpServerObject.onOpen

```aardio aardio
asynHttpServerObject.onOpen = function(hSocket,err){
    var client = asynHttpServerObject.client(hSocket);

    /*已连�?在这里可以开始发送数�?/
}

```

### asynHttpServerObject.onOutOfBandData

```aardio aardio
asynHttpServerObject.onOutOfBandData = function(hSocket,err){
    var client = asynHttpServerObject.client(hSocket);

    /*收到紧急数�?即send函数最后一个flag参数设为_MSG_OOB时发送的1字节带外数据*/
}

```

### asynHttpServerObject.onRead

```aardio aardio
asynHttpServerObject.onRead = function(hSocket,err){
    var client = asynHttpServerObject.client(hSocket);

    /*收到数据
可阻塞读取数�?定义了此事件就不应同时定义onReceive事件*/
}

```

### asynHttpServerObject.onReceive

```aardio aardio
asynHttpServerObject.onReceive = function(hSocket,err){
    var client = asynHttpServerObject.client(hSocket);

    /*收到数据
仅读取已到达的数�?定义了此事件就不应同时定义onRead事件*/
}

```

### asynHttpServerObject.onSend

```aardio aardio
asynHttpServerObject.onSend = function(hSocket,err){
    var client = asynHttpServerObject.client(hSocket);

    /*发送数�?/
}

```

### asynHttpServerObject.onStop

```aardio aardio
asynHttpServerObject.onStop = function(err){

    /*已停止服务端
主动调用stop函数停止服务端时不会触发此事�?/
}

```

### asynHttpServerObject.onUpgradeProtocol

```aardio aardio
asynHttpServerObject.onUpgradeProtocol = function(client,request,response){
    /*处理客户端升级协议请�?
可在此回调中切换到WebSocket协议*/
}

```

### asynHttpServerObject.run(httpProc)

```aardio aardio
asynHttpServerObject.run(
    function(response,request,session){
         response.loadcode(request.path);
    }/*启动HTTP服务并在此回调函数中处理请求�?不传入参数则默认调用response.loadcode �?也可以传入一个或多个表参�?键为页面相对路径,值为响应数据或回调函�?
键指定的路径�?aardio 后缀时，启用模板语法解析并返�?HTML 代码*/
);

```

### asynHttpServerObject.serverAddress

服务端监听地址

[返回对象:sockaddrInObject](#sockaddrInObject)

### asynHttpServerObject.shutdown()

断开 HTTP 服务�?
### asynHttpServerObject.spaUrl

返回 SPA 单页应用首页网址

如未启动服务端则自动启动且监听IP设为 "127.0.0.1"

### asynHttpServerObject.spaUrl(indexHtmlPath,documentBase)

参数指定 SPA 单页应用首页路径�?
404错误页也会自动设置到该路径，

返回首页网址

可选用参数 @documentBase 指定根目录以避免网页不支持非根目录路�?
### asynHttpServerObject.start(IP,端口,请求队列大小)

启动单线程异步TCP服务�?成功返回true,失败返回null,

如果不写IP，则默认设为"0.0.0.0"也即监听本机所有IP,访问此服务端也不限制IP

限制仅本机可以访问建议写127.0.0.1

端口�?或省略则自动查找1025以后的空闲端�?
注意0-1023为系统通用服务保留端口,

1024-49151为用户服务端�?其中大约%9已由IANA注册分配

49152-65535为私有或临时端口

### asynHttpServerObject.stop()

关闭 HTTP 服务�?
## asynHttpServerObject.clients 成员列表

这是一个包含所有客户端套接字的表对�?
其中键为套接字句�?值为 wsock.tcp.asynClient对象

### asynHttpServerObject.clients.?

[返回对象:tcpaclientObject](asynClient.html#tcpaclientObject)

## wsock.tcp 成员列表

### wsock.tcp.asynHttpServer

单线程异�?HTTP 服务�?
浏览器组件发起异�?HTTP 请求支持 asynHttpServer�?
请不要用 inet.http 等阻塞请求同一线程创建�?asynHttpServer,

这会导致 asynHttpServer 没有机会响应请求而导致死锁，

一般没必要这样自己 HTTP 请求自己，改成普通函数调用即可，

如果确有这样的需求，可以创建线程调用 inet.http 发起请求�?
或改用基于多线程�?wsock.tcp.simpleHttpServer 创建服务�?
### wsock.tcp.asynHttpServer()

创建单线程异�?HTTP 服务�?
[返回对象:asynHttpServerObject](asynHttpServer.html#asynHttpServerObject)

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/wsock/tcp/asynHttpServer.md)

