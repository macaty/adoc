[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# web.socket.server 库模块帮助文�?
## web.socket.server 成员列表

支持单线程异步的WebSocket服务�?
可直接在界面线程中使用，不会阻塞界面，不需要创建多线程

支持服务端心�?Ping/Pong�?，客户端单向心跳(Pong�?机制,

可调用close函数断线，并可调用connect函数实现重析连接服务�?
### web.socket.server.getSecAccept()

获取WebSocket客户端配对密钥，

参数指定服务端HTTP头中sec-websocket-accept返回的�?
### web.socket.server.getSecKey()

获取WebSocket客户端密�?
### web.socket.server.sha1()

使用sha1算法取哈希值，并使用Base64编码为普通文�?
## web.socket 成员列表

### web.socket.server()

[返回对象:websocketserverObject](#websocketserverObject)

## websocketserverObject 成员列表

### websocketserverObject.\_beforeStop

```aardio aardio
websocketserverObject._beforeStop = function(){
    /*服务端关闭以前触�?此回调函数是标准库保留接�?用户不应使用此回�?/
}

```

### websocketserverObject.\_onClientClosed

```aardio aardio
websocketserverObject._onClientClosed = function(hSocket){
    /*客户端连接已经关闭时触发�?hSocket 参数为客户端连接套接字句柄，
此函数在连接断开后一定会被触发，
此回调函数是标准库保留接口，
用户不应使用此回�?/
}

```

### websocketserverObject.\_translateMessage

此回调函数的参数与onMessage相同,

如果定义了这个回调函�?

那么此函数将在调用onMessage之前被调�?

如果此回调返回true则不再触发onMessage,

这个函数提供了一个机会用于自动处理客户端消息

,为其他需要扩展web.socket.server功能的库所预留�?
一旦定义将不能修改

### websocketserverObject.beforeStop

```aardio aardio
websocketserverObject.beforeStop = function(){
    /*服务端关闭以前触�?/
}

```

### websocketserverObject.client()

[返回对象:tcpaclientObject](../../wsock/tcp/asynClient.html#tcpaclientObject)

### websocketserverObject.client(hSocket)

使用 @hSocket 参数指定的客户端连接套接字句�?
获取 wsock.tcp.client 对象

### websocketserverObject.clientCount()

当前WebSocket客户端数�?
包含正在连接或正在断开连接的客户端

不含已关闭的客户�?
### websocketserverObject.close(hSocket,code,reason)

关闭连接,

@hSocket 参数指定客户端连接套接字句柄

### websocketserverObject.getLocalIp()

返回当前绑定�?IP,端口�?
### websocketserverObject.getRemoteIp(hSocket)

返回客户端IP地址,端口,

@hSocket 参数指定客户端连接套接字句柄

### websocketserverObject.getUrl()

获了服务端网址,可选指定目录或文件路径

注意参数第一个字符不需要指定斜�?
如果参数@2为true，IP "0.0.0.0"替换为上网卡IP而不是localhost

如果服务器启动失败不返回任何�?
### websocketserverObject.heartbeatData

心跳帧发送的数据,默认为空数据

这个值修改以后，只能在下次调用connect函数才会生效

### websocketserverObject.heartbeatInterval

服务端主动发送心跳Ping空帧间隔,默认�?0分钟

设为-1时禁用客户端心跳,一般不建议禁用

这个值修改以后，只能在下次调用start函数才会生效

### websocketserverObject.heartbeatType

心跳帧发送的的帧类型,

默认�?,也就是Ping�?
这个值修改以后，只能在下次调用start函数才会生效

### websocketserverObject.httpServer

单线程异�?HTTP服务�?wsock.tcp.asynHttpServer对象

浏览器组件发起异�?HTTP 请求支持 wsock.tcp.asynHttpServer�?
请不要用 inet.http 等阻塞请求同一线程创建�?asynHttpServer,

这会导致 asynHttpServer 没有机会响应请求而导致死锁，

如果确有这样的需求，可创建线程发起请求，

或改用基于多线程�?wsock.tcp.simpleHttpServe,

[返回对象:asynHttpServerObject](../../wsock/tcp/asynHttpServer.html#asynHttpServerObject)

### websocketserverObject.isClosed(hSocket)

连接是否已关�?

@hSocket 参数指定客户端连接套接字句柄

### websocketserverObject.isConnected(hSocket)

是否已连接并准备就绪可以发送数�?

@hSocket 参数指定客户端连接套接字句柄

### websocketserverObject.onClientClosed

```aardio aardio
websocketserverObject.onClientClosed = function(hSocket){
    /*客户端连接已经关闭时触发,
hSocket 参数为客户端连接套接字句�?
此函数在连接断开后一定会被触�?/
}

```

### websocketserverObject.onClose

```aardio aardio
websocketserverObject.onClose = function(hSocket,err){
    /*连接被关�?
hSocket 参数为客户端连接套接字句�?
err.code 为错误代�?err.reason 为错误原�?客户端关闭连接并不保证一定会触发此消�?但onClientClosed事件在关闭后一定会被触�?/
}

```

### websocketserverObject.onError

```aardio aardio
websocketserverObject.onError = function(hSocket,err){
    /*发生错误,
hSocket 参数指定客户端连接套接字句柄,
err为错误信�?/
}

```

### websocketserverObject.onFragment

```aardio aardio
websocketserverObject.onFragment = function(hSocket,msg){
   /*收到分片数据,
hSocket 参数指定客户端连接套接字句柄,
第一个数据包使用msg.type指明类型,参考WebSocket协议规范
后续数据包msg.type�?,最后一个数据包msg.fin�?

如果不指定这个回调函�?则自动并接分片数据后触发onMessage事件*/
}

```

### websocketserverObject.onMessage

```aardio aardio
websocketserverObject.onMessage = function(hSocket,msg){
    /*收到服务端数�?
hSocket 参数指定客户端连接套接字句柄,
msg.type�?时msg.data为文�?
否则msg.data为字节数组（buffer类型�?/

}

```

### websocketserverObject.onOpen

```aardio aardio
websocketserverObject.onOpen = function(hSocket){
    /*客户端已切换到WebSocket服务�?hSocket 参数为客户端连接套接字句�?/
}

```

### websocketserverObject.onUpgradeToWebsocket

```aardio aardio
websocketserverObject.onUpgradeToWebsocket = function(hSocket,request,response,protocol,origin){
    /*
用户发送HTTP请求切换到WebSocket协议,
可以在这里修改HTTP响应头中Sec-WebSocket-Protocol的�?
如果要阻止用户切换到WebSocket,�?response.close() 关闭请求�?或调�?response.errorStatus() 函数返回错误代码即可�?否则退出此函数后会继续切换到WebSocket协议�?
参数说明:
hSocket为客户端套接字句�?request为HTTP请求对象
response为HTTP应答对象
protocol为Sec-WebSocket-Protocol请求头的�?/
}

```

### websocketserverObject.publish()

发送数据给所有的客户�?

支持字符串或 buffer、结构体

字符串作为UTF8文本类型发�?其他以二进制类型发送，

成功返回true

### websocketserverObject.send(hSocket,)

发送数�?支持字符串或 buffer、结构体

字符串作为UTF8文本类型发�?其他以二进制类型发�?

@hSocket 参数指定客户端连接套接字句柄�?
成功返回true

### websocketserverObject.sendData(hSocket,data,opcode,fin,rsv1,rsv2,rsv3)

发送WebSocket数据�?
参数@1支持支持字符串或 buffer、结构体

除参数@1以外,所以参数可�?
一般应当调用send函数，而不是调用sendData函数

如果一定要使用这个函数,请阅读此函数源码,以及 WebSocket 协议相关说明

### websocketserverObject.start(IP,端口,请求队列大小)

启动单线程异�?WebSocket 服务�?成功返回 true,失败返回 null,

如果不写IP，则默认设为"0.0.0.0"也即监听本机所有IP,访问此服务端也不限制IP

限制仅本机可以访问建议写127.0.0.1

端口�?或省略则自动查找1025以后的空闲端�?
注意0-1023为系统通用服务保留端口,

1024-49151为用户服务端�?其中大约%9已由IANA注册分配

49152-65535为私有或临时端口

### websocketserverObject.stop()

WebSocket服务�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/web/socket/server.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/web/socket/server.md')

