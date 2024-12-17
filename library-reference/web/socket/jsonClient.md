[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# web.socket.jsonClient 库模块帮助文�?
## WebSocketJsonClientObject 成员列表

### WebSocketJsonClientObject.?

远程对象名或远程方法名字,

作为函数调用时返回一个调用对�?

通过指定返回调用对象�?end 属性定义调用结束回调函�?例如:

ret.end=function(result,err){

}

回调参数 result 为调用返回�?err 为错误信�?

如果调和成功,err参数为null

[返回对象:WebSocketJsonClientObject](jsonClient.html#WebSocketJsonClientObject)

### WebSocketJsonClientObject.done

通过远程函数调用返回对象�?done 属性判断调用是否完成�?
注意出错时则 done 可能不会设为 true，应�?rpc.onError 回调中处理这种情况�?
### WebSocketJsonClientObject.end

```aardio aardio
WebSocketJsonClientObject.end = function(result,err){
    /*可通过远程函数调用返回对象�?end 属性指定一个调用完成触发的回调函数�?回调参数 result 为远程调用返回�?err 为错误对�?
调用成功 err 参数为null*/
}

```

### WebSocketJsonClientObject.rpc

WebSocket客户端对�?
此对象的成员谨慎改动

[返回对象:websocketjsonClientrpcObject](#websocketjsonClientrpcObject)

## web.socket 成员列表

### web.socket.jsonClient

WebSocket / JSON-RPC 2.0 单线程异步客户端

### web.socket.jsonClient()

[返回对象:websocketjsonClientObject](#websocketjsonClientObject)

## websocketjsonClientObject 成员列表

### websocketjsonClientObject.?

远程对象名或远程方法名字,

[返回对象:WebSocketJsonClientObject](jsonClient.html#WebSocketJsonClientObject)

### websocketjsonClientObject.connect("ws://")

重新连接到WebSocket服务�?
参数指定WebSocket服务端网址，例�?"ws://localhost:7511"

如果不指定参�?则获取上次调用此函数指定的网址参数,

如果之前也没有指定网址则抛出异�?
### websocketjsonClientObject.on("close",proc)

```aardio aardio
websocketjsonClientObject.on("close",function(e){
    /*连接被关�?e.code为错误代码e.reason为错误原�?/
})

```

### websocketjsonClientObject.on("error",proc)

```aardio aardio
websocketjsonClientObject.on("error",function(errMessage,rpcError){
    /*发生错误,errMessage 为错误信息�?如果服务端按 jsonrpc 协议返回 error 对象�?�?rpcError 有值，包含 messge，code 字段�?/
})

```

### websocketjsonClientObject.on("fragment",proc)

```aardio aardio
websocketjsonClientObject.on("fragment",function(msg){
   /*收到分片数据
第一个数据包使用msg.type指明类型,参考WebSocket协议规范
后续数据包msg.type�?,最后一个数据包msg.fin�?

如果不指定这个回调函�?则自动并接分片数据后触发onMessage事件*/
})

```

### websocketjsonClientObject.on("message",proc)

```aardio aardio
websocketjsonClientObject.on("message",function(msg){
    /*收到服务端数�?msg.type�?时msg.data为文�?
否则msg.data为字节数组（buffer类型�?/
})

```

### websocketjsonClientObject.on("open",proc)

```aardio aardio
websocketjsonClientObject.on("open",function(){
    /*已打开连接*/
}

```

### websocketjsonClientObject.on(method,proc)

```aardio aardio
websocketjsonClientObject.on("/*需要监听的Rpc通知事件名字*/",function(param){

})

```

### websocketjsonClientObject.rpc

WebSocket客户端对�?
此对象的成员谨慎改动

[返回对象:websocketjsonClientrpcObject](#websocketjsonClientrpcObject)

## websocketjsonClientrpcObject 成员列表

### websocketjsonClientrpcObject.afterJsonStringify

```aardio aardio
websocketjsonClientrpcObject.afterJsonStringify = function(jsonData){
    /*可以在这里加密客户端JSON,返回null中止本次调用*/
    return jsonData;
}

```

### websocketjsonClientrpcObject.beforeJsonParse

```aardio aardio
websocketjsonClientrpcObject.beforeJsonParse = function(jsonData){
    /*可以在这里解密服务端数据,返回null中止本次调用*/
    return jsonData;
}

```

### websocketjsonClientrpcObject.beforeRequest(请求数据)

```aardio aardio
websocketjsonClientrpcObject.beforeRequest = function(reqData){
    /*此回调事件在发送请求前触发
reqData.params是即将发送的参数*/
    return reqData;
}

```

### websocketjsonClientrpcObject.beginTrans()

开始批量调�?
之后的所有RPC调用不提交服务器,

直到调用commitTrans函数

### websocketjsonClientrpcObject.close()

关闭连接

可选增�?个参数指定发送给服务器的关闭帧附加数�?

参数@1为数值类型的错误代码,参数@2为字符串类型错误描述

### websocketjsonClientrpcObject.commitTrans()

完成批量调用并提交到服务�?
### websocketjsonClientrpcObject.connect("ws://")

重新连接到WebSocket服务�?
参数指定WebSocket服务端网址，例�?"ws://localhost:7511"

如果不指定参�?则获取上次调用此函数指定的网址参数,

如果之前也没有指定网址则抛出异�?
### websocketjsonClientrpcObject.headers

其他HTTP请求�?
值可以是文本或数组、或键值对组成的表

请求时会调用 web.joinHeaders()函数拼接并转换HTTP�?
该函数支持的类型和格式这个属性都可以支持

### websocketjsonClientrpcObject.heartbeatData

单向心跳发送的数据,默认为空数据

这个值修改以后，只能在下次调用connect函数才会生效

### websocketjsonClientrpcObject.heartbeatInterval

客户端主动发送心跳间�?默认�?0�?

设为-1时禁用客户端心跳,注意某些服务端收到心跳包会报�?这时建议关掉心跳,

此属性值修改以后，只能在下次调用connect函数才会生效

### websocketjsonClientrpcObject.heartbeatType

单向心跳发送的的帧类型,

默认�?xA,也就是单向心�?Pong �?
这个值修改以后，只能在下次调用connect函数才会生效

### websocketjsonClientrpcObject.isClosed()

套接字是否已关闭

### websocketjsonClientrpcObject.isConnected()

套接字是否已连接并准备就�?已与服务器握手成�?

### websocketjsonClientrpcObject.originUrl

浏览器启动WebSocket客户端的网址

一些WebSocket服务器根据这个判断是不是允许连接,

所以有时候设置这个很重要

默认使用WebSocket网址，并�?前面的ws://改为http://

### websocketjsonClientrpcObject.protocol

应用程序支持的协议列�?默认�?chat"

### websocketjsonClientrpcObject.readyState

连接状�?

0为等待连�?1为已连接并准备就�?2为正在关�?3为已关闭

只有成功通过WebSocket协议握手以后readyState才会被置�?

这与socket.readyState连接成功就会置为1是不同的

### websocketjsonClientrpcObject.responseHeaders

服务端响应的HTTP�?
这是一个表对象，键名都已转为小�?
### websocketjsonClientrpcObject.rollbackTrans()

撤消尚未提交的批量调�?
### websocketjsonClientrpcObject.socket

异步套接字对�?
在关闭连接状态下此属性的值为null

应由对象自动打开或删除套接字对象，调用者不可改动此属性的�?
[返回对象:tcpaclientObject](../../wsock/tcp/asynClient.html#tcpaclientObject)

### websocketjsonClientrpcObject.url

上次成功连接的网址

也可以用于指定下次连接的默认网址

### websocketjsonClientrpcObject.userAgent

客户端应用程序代理头

默认�?Mozilla/5.0"

### websocketjsonClientrpcObject.varargs

默认值为true,

值为true时将不定个数的参数放入数组发送给服务�?
值为false时直接将单个参数发送给服务�?
JSON-RPC 2.0一个会制造混乱的地方�?
如果params是一个数组，并没有规定是展开为一个参数，还是作为一个数组参数�?
目前aardio的RPC服务端会负责展开数组作为多个参数�?
但客户端需要在这里手动设置

### websocketjsonClientrpcObject.version

值为JSON-RPC协议版本�?2.0"

不应该修改这个�?
### websocketjsonClientrpcObject.waitForConnected(关联窗口句柄,超时)

等待连接到WebSocket服务�?
所有参数可�?超时以毫秒为单位,

连接成功返回true,失败返回false或null

### websocketjsonClientrpcObject.xcall(method,param)

```aardio aardio
websocketjsonClientrpcObject.xcall("Page.navigate",{
    url = "网址"
}).end = function(result,err){
    /*调用JSON-RPC服务端的指定方法
服务器应答后回调此函数返回值的成员函数:end函数
end函数�?个回调参�?参数@1为result，参数@2为err
失败err参数非空*/
}

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/web/socket/jsonClient.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/web/socket/jsonClient.md')

