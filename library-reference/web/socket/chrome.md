[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# web.socket.chrome 库模块帮助文�?
## web.socket.chrome 成员列表

chrome远程调试接口

WebSocket / JSON-RPC 2.0 单线程异步客户端

[chrome远程调试接口文档](javascript:if(confirm('https://chromedevtools.github.io/devtools-protocol/  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ����һ������·���ⲿ������Ϊ������ʼ��ַ�ĵ�ַ��  \n\n�����ڷ������ϴ�����?'))window.location='https://chromedevtools.github.io/devtools-protocol/')

### web.socket.chrome.lastRemoteDebuggingPort

最近连接的远程调试端口号，也可以使用些属性指定下次连接远程调试服务端使用的默认端�?
## web.socket 成员列表

### web.socket.chrome()

创建chrome远程调试客户�?
[返回对象:websocketchromeClientObject](#websocketchromeClientObject)

## websocketchromeClientObject 成员列表

### websocketchromeClientObject.?

远程对象名或远程方法名字,

作为函数调用时返回一个调用对�?

通过指定返回调用对象�?end 属性定义调用结束回调函�?例如:

ret.end=function(result,err){

}

回调参数 result 为调用返回�?err 为错误信�?

如果调和成功,err参数为null

[返回对象:WebSocketJsonClientObject](jsonClient.html#WebSocketJsonClientObject)

### websocketchromeClientObject.connect("ws://")

重新连接到WebSocket服务�?
参数指定WebSocket服务端网址，例�?"ws://localhost:7511"

如果不指定参�?则获取上次调用此函数指定的网址参数,

如果之前也没有指定网址则尝试自动查找可用接口地址

如果存在可用的远程接口地址,此函数返回true,否则返回null

但返回true并不表示连接成功,应在open事件中判断是否连接成�?
chrome的远程调试接口必须是独占模式,

chrome开发工具连上去�?再连接就会失�?
chrome在整个系统只能用一个端口，启动一个开发工�?
但是electron可以每个进程使用自己的端�?启动一个独立的远程调试接口

### websocketchromeClientObject.connectFirstDebuggingPage()

连接到指定端口的首个有效调试页面对象,

参数指定远程调试端口号，或者拥有remoteDebuggingPort属性的对象

### websocketchromeClientObject.eachDebuggingPage(port)

```aardio aardio
for id,title,wsUrl,devtoolsUrl in websocketchromeClientObject.eachDebuggingPage(/*参数指定远程调试端口号，或者拥有remoteDebuggingPort属性的对象*/) {

}

```

### websocketchromeClientObject.getDebuggingInfo()

用于获取远程调试服务端信�?
参数指定远程调试端口号，或者拥有remoteDebuggingPort属性的对象

返回的参数是一个数�?即使失败也会返回空数�?
每个元素是一个表

### websocketchromeClientObject.getDebuggingPages()

用于获取所有可以远程调试的页面对象

参数指定远程调试端口号，或者拥有remoteDebuggingPort属性的对象

返回的参数是一个数�?即使失败也会返回空数�?
每个元素是页面信息表

### websocketchromeClientObject.isClosed()

套接字是否已关闭

### websocketchromeClientObject.isConnected()

套接字是否已连接并准备就�?已与服务器握手成�?

### websocketchromeClientObject.on("close",proc)

```aardio aardio
websocketchromeClientObject.on("close",function(e){
    /*连接被关�?e.code为错误代码e.reason为错误原�?/
})

```

### websocketchromeClientObject.on("error",proc)

```aardio aardio
websocketchromeClientObject.on("error",function(err){
    /*发生错误,err为错误信�?/
})

```

### websocketchromeClientObject.on("fragment",proc)

```aardio aardio
websocketchromeClientObject.on("fragment",function(msg){
   /*收到分片数据
第一个数据包使用msg.type指明类型,参考WebSocket协议规范
后续数据包msg.type�?,最后一个数据包msg.fin�?

如果不指定这个回调函�?则自动并接分片数据后触发onMessage事件*/
})

```

### websocketchromeClientObject.on("message",proc)

```aardio aardio
websocketchromeClientObject.on("message",function(msg){
    /*收到服务端数�?msg.type�?时msg.data为文�?
否则msg.data为字节数组（buffer类型�?/
})

```

### websocketchromeClientObject.on("open",proc)

```aardio aardio
websocketchromeClientObject.on("open",function(){
    /*已打开连接*/
}

```

### websocketchromeClientObject.on(method,proc)

```aardio aardio
websocketchromeClientObject.on("/*需要监听的Rpc通知事件名字*/",function(param){

})

```

### websocketchromeClientObject.readyState

连接状�?

0为等待连�?1为已连接并准备就�?2为正在关�?3为已关闭

只有成功通过WebSocket协议握手以后readyState才会被置�?

这与socket.readyState连接成功就会置为1是不同的

### websocketchromeClientObject.rpc

WebSocket客户端对�?
此对象的成员谨慎改动

[返回对象:websocketjsonClientrpcObject](#websocketjsonClientrpcObject)

### websocketchromeClientObject.waitForConnected(关联窗口句柄,超时)

等待连接到远程调试接�?
所有参数可�?超时以毫秒为单位,

如果没有找到有效的接口地址,

此函数会自动发现嵌入electron的远程接口地址并重试连�?
连接成功返回true,失败返回false或null

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/web/socket/chrome.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/web/socket/chrome.md')

