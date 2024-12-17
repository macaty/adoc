[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# web.socket.jsonServer 库模块帮助文�?
## web.socket 成员列表

### web.socket.jsonServer

创建WebSocket/JSON-RPC 2.0服务�?
### web.socket.jsonServer()

[返回对象:websocketjsonserverObject](#websocketjsonserverObject)

### web.socket.jsonServer(wsServer,external)

创建WebSocket/JSON-RPC 2.0服务�?
参数@1应当是一�?web.socket.server对象

参数@2指定客户端可以调用的表对�?
external也可以在创建对象以后,使用对象的external属性指�?
## websocketjsonserverObject 成员列表

### websocketjsonserverObject.aasdl

指定自定义的aasdl

如果客户端请求的方法名为"?"�?返回此属�?

[关于aasdl](javascript:if(confirm('https://github.com/aardio/aardio-js/blob/master/AASDL.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ����һ������·���ⲿ������Ϊ������ʼ��ַ�ĵ�ַ��  \n\n�����ڷ������ϴ�����?'))window.location='https://github.com/aardio/aardio-js/blob/master/AASDL.md')

### websocketjsonserverObject.afterJsonStringify

```aardio aardio
websocketjsonserverObject.afterJsonStringify = function(jsonData){
    /*可以在这里加密服务端数据,返回null中止本次调用*/
    return jsonData;
}

```

### websocketjsonserverObject.beforeJsonParse

```aardio aardio
websocketjsonserverObject.beforeJsonParse = function(hSocket,jsonData){
    /*可以在这里解密客户端数据,返回null中止本次调用*/
    return jsonData;
}

```

### websocketjsonserverObject.external

指定包含客户端可以调用的远程函数的表对象,可嵌套子�?
如果远程函数名第一个字符是$,则第一个回调参数为hSocket,用于表示当前发送请求的客户端套接字,

如果客户端请求方法名�??"时，并且服务端没有指定aasdl属�?
服务端会根据aasdl协议将对象序列化为json并返回客户端�?
[关于aasdl](javascript:if(confirm('https://github.com/aardio/aardio-js/blob/master/AASDL.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ����һ������·���ⲿ������Ϊ������ʼ��ַ�ĵ�ַ��  \n\n�����ڷ������ϴ�����?'))window.location='https://github.com/aardio/aardio-js/blob/master/AASDL.md')

### websocketjsonserverObject.hActiveSocket

获取当前活动的客户端套接字句�?

应当在RPC回调的第一句代码中获取此句�?

因为执行其他代码都有可能导致其他客户端变为活动客户端

### websocketjsonserverObject.isClosed(hSocket)

连接是否已关�?
### websocketjsonserverObject.isConnected(hSocket)

是否已连接并准备就绪可以发送数�?
### websocketjsonserverObject.notify(hSocket,method,...)

主动向客户端发送通知

参数hSocket指定客户端套接字句柄,

method指定客户端方法名,

可添加任意个调用参数

### websocketjsonserverObject.publish(method,...)

主动向所有客户端发送通知

method指定客户端方法名,

可添加任意个调用参数

### websocketjsonserverObject.send(hSocket,rep)

对指定的套接字发送数�?

参数hSocket指定客户端套接字句柄,

rep应当是符合JSON-RPC 2.0编码协议的响应对�?
不建议直接调用此函数发送消�?
### websocketjsonserverObject.start(hSocket)

对指定的套接字启动JSON-RPC服务

参数hSocket指定客户端套接字句柄,

hSocket参数必须在web.socket.server服务端对�?
的onUpgradeToWebsocket事件中获�?
### websocketjsonserverObject.survey(method,...)

发起调查任务,

调用所有客户端的同名函�?

method指定客户端方法名,

可添加任意个调用参数

客户端会触发xcallback的成员函数，

请参考xcallback的说�?
### websocketjsonserverObject.version

JSON-RPC版本号，不应改动

### websocketjsonserverObject.wsServer

web.socket.server服务端对�?
### websocketjsonserverObject.xcall(hSocket,method,...)

主动调用客户端函�?
参数hSocket指定客户端套接字句柄,

method指定客户端方法名,

可添加任意个调用参数

客户端会触发xcallback的成员函数，

请参考xcallback的说�?
## websocketjsonserverObject.web.socket 成员列表

### websocketjsonserverObject.web.socket.jsonServer

创建WebSocket/JSON-RPC 2.0服务�?
## websocketjsonserverObject.xcallback 成员列表

服务端通过xcall函数调用客户端函数时

客户端如果返回应答会自动回调xcallback的成员函�?
### websocketjsonserverObject.xcallback.?

```aardio aardio
websocketjsonserverObject.xcallback./*出错时err为错误对�?
否则result为客户端返回的�?hSocket为客户端套接�?/ = function(hSocket,result,err){

}

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/web/socket/jsonServer.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/web/socket/jsonServer.md')

