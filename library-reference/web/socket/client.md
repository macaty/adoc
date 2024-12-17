[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# web.socket.client 库模块帮助文�?
## web.socket.client 成员列表

支持单线程异步的 WebSocket 客户�?
可直接在界面线程中使用，不会阻塞界面，不需要创建多线程

支持服务端心�?Ping/Pong�?，客户端单向心跳(Pong�?机制,

可调�?close 函数断线，并可调�?connect 函数实现重析连接服务�?
### web.socket.client.getSecAccept()

获取WebSocket客户端配对密钥，

参数指定服务端HTTP头中sec-websocket-accept返回的�?
### web.socket.client.getSecKey()

获取WebSocket客户端密�?
### web.socket.client.sha1()

使用sha1算法取哈希值，并使用Base64编码为普通文�?
## web.socket 成员列表

�?aardio 代码实现的轻�?WebSocket 组件�?
仅支�?ws 协议，改�?web.SocketSharp 可支�?wss 协议

### web.socket.client()

[返回对象:websocketclientObject](#websocketclientObject)

## websocketclientObject 成员列表

### websocketclientObject.\_translateMessage

此回调函数的参数与onMessage相同,

如果定义了这个回调函�?

那么此函数将在调用onMessage以后被调�?

这个函数提供了一个机会用于自动处理服务器消息

,为其他需要扩展web.socket.client功能的库所预留�?
一旦定义将不能修改

### websocketclientObject.close()

关闭连接

可选增�?个参数指定发送给服务器的关闭帧附加数�?

参数@1为数值类型的错误代码,参数@2为字符串类型错误描述

### websocketclientObject.connect("ws://")

重新连接到WebSocket服务�?
参数指定WebSocket服务端网址，例�?"ws://localhost:7511"

如果不指定参�?则获取上次调用此函数指定的网址参数,

如果之前也没有指定网址则抛出异�?
### websocketclientObject.headers

其他HTTP请求�?
值可以是文本或数组、或键值对组成的表

请求时会调用 web.joinHeaders()函数拼接并转换HTTP�?
该函数支持的类型和格式这个属性都可以支持

### websocketclientObject.heartbeatData

单向心跳发送的数据,默认为空数据

这个值修改以后，只能在下次调用connect函数才会生效

### websocketclientObject.heartbeatInterval

客户端主动发送心跳间�?默认�?0�?

设为-1时禁用客户端心跳,注意某些服务端收到心跳包会报�?这时建议关掉心跳,

此属性值修改以后，只能在下次调用connect函数才会生效

### websocketclientObject.heartbeatType

单向心跳发送的的帧类型,

默认�?xA,也就是单向心�?Pong �?
这个值修改以后，只能在下次调用connect函数才会生效

### websocketclientObject.isClosed()

套接字是否已关闭

### websocketclientObject.isConnected()

套接字是否已连接并准备就�?已与服务器握手成�?

### websocketclientObject.onClose

```aardio aardio
websocketclientObject.onClose = function(e){
    /*连接被关�?e.code为错误代码e.reason为错误原�?/
}

```

### websocketclientObject.onError

```aardio aardio
websocketclientObject.onError = function(err){
    /*发生错误,err为错误信�?/
}

```

### websocketclientObject.onFragment

```aardio aardio
websocketclientObject.onFragment = function(msg){
   /*收到分片数据
第一个数据包使用msg.type指明类型,参考WebSocket协议规范
后续数据包msg.type�?,最后一个数据包msg.fin�?

如果不指定这个回调函�?则自动并接分片数据后触发onMessage事件*/
}

```

### websocketclientObject.onMessage

```aardio aardio
websocketclientObject.onMessage = function(msg){
    /*收到服务端数�?msg.type�?时msg.data为文�?
否则msg.data为字节数组（buffer类型�?/

}

```

### websocketclientObject.onOpen

```aardio aardio
websocketclientObject.onOpen = function(){
    websocketclientObject.send("已连接到WebSocket服务");
}

```

### websocketclientObject.originUrl

浏览器启动WebSocket客户端的网址

一些WebSocket服务器根据这个判断是不是允许连接,

所以有时候设置这个很重要

默认使用WebSocket网址，并�?前面的ws://改为http://

### websocketclientObject.protocol

应用程序支持的协议列�?默认�?chat"

### websocketclientObject.readyState

连接状�?

0为等待连�?1为已连接并准备就�?2为正在关�?3为已关闭

只有成功通过WebSocket协议握手以后readyState才会被置�?

这与socket.readyState连接成功就会置为1是不同的

### websocketclientObject.responseHeaders

服务端响应的HTTP�?
这是一个表对象，键名都已转为小�?
### websocketclientObject.secKey

连接密钥,不可改动

### websocketclientObject.send()

发送数�?支持字符串或 buffer、结构体

字符串作为UTF8文本类型发�?其他以二进制类型发送，

成功返回true

### websocketclientObject.sendData(data,opcode,fin,mask,rsv1,rsv2,rsv3)

发送WebSocket数据�?
参数@1支持支持字符串或 buffer、结构体

除参数@1以外,所以参数可�?
一般应当调用send函数，而不是调用sendData函数

如果一定要使用这个函数,请阅读此函数源码,以及WebSocket协议相关说明

### websocketclientObject.socket

异步套接字对�?
在关闭连接状态下此属性的值为null

应由对象自动打开或删除套接字对象，调用者不可改动此属性的�?
[返回对象:tcpaclientObject](../../wsock/tcp/asynClient.html#tcpaclientObject)

### websocketclientObject.url

上次成功连接的网址

也可以用于指定下次连接的默认网址

### websocketclientObject.userAgent

客户端应用程序代理头

默认�?Mozilla/5.0"

### websocketclientObject.waitForConnected(关联窗口句柄,超时)

等待连接到WebSocket服务�?
所有参数可�?超时以毫秒为单位,

连接成功返回true,失败返回false或null

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/web/socket/client.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/web/socket/client.md')

