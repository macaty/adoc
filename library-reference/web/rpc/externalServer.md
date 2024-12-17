[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# web.rpc.externalServer 库模块帮助文�?
用法说明

1、在 aardio 编写的本地软件中创建 RPC 服务�?var rpcServer = web.rpc.externalServer()
rpcServer.start();

2、使�?rpcServer.getUrl("aardio.js") 取得 aardio.js 的地址�?并在网页中使用该地址加载 aardio.js

3、网页如果使用了 typescript，源码工程中添加 global.d.ts 内容如下�?
```
declare global {

    interface aardioExternal {
    /* 添加 external 接口导出�?aardio  函数 */
    test: (name: string,value: number) => Promise<string>;
    }
}
export {};

```

4、打开远程网页则必须在 URL 中通过 rpcServerPort 参数指定 RPC 服务端口号，
必须�?JavaScript 中调�?aardio.open() 连接 RPC 服务端，并在 aardio.ready 回调中使�?RPC 函数�?
如果要限制调�?aardio 函数的域名，可以这样写：

```
rpcServer.accessControlAllowOrigin = {
    ["https://example.com"] = true //域名后不要加斜杆
}

```

## web.rpc 成员列表

### web.rpc.externalServer

创建可在普通网页浏览器引入�?aardio 本地软件交互�?RPC 服务�?
建议服务端IP保持默认�?127.0.0.1�?
即可在任意网页中调用 aardio.js 并导�?aardio 对象,

可嵌�?HTTPS 网页

### web.rpc.externalServer()

创建可在普通网页浏览器引入�?aardio 本地软件交互�?RPC 服务�?

可自动支持标准库 nodeJs

[返回对象:webRpcExternalServerObject](#webRpcExternalServerObject)

## webRpcExternalServerObject 成员列表

### webRpcExternalServerObject.accessControlAllowOrigin

允许写入 Access-Control-Allow-Headers 响应头的站点地址�?
此属性必须为 null、字符串，或者指定为一个表对象,

表的键为允许跨域调用的站点地址,值必须为 true

站点地址应使�?https://host 格式，且结尾不要有斜杠，

新的浏览器已经禁止在�?HTTPS 协议下调用本机地址�?
而老版浏览器则反之

### webRpcExternalServerObject.accessControlRequestPrivateNetwork

自定�?Access-Control-Request-Private-Network 响应头的值，

默认�?"true"，可改为 null

### webRpcExternalServerObject.callback(name,callback)

```aardio aardio
webRpcExternalServerObject.callback("/*要接收返回值的JS函数�?
回调叁数$为RPC客户端套接字句柄
成功result为返回�?失败err为错误信�?/",function($,result,err){

})

```

### webRpcExternalServerObject.doScript($,js,...)

在chrome中执行javascript代码,忽略返回�?

在js参数后可选指定多个字符串格式化参数用于调用string.form格式化代�?

参数@1指定客户端套接字句柄,

RPC服务端远程回调函数名首字符为$�?

第一个回�?参数即为当前客户端套接字句柄,

除非熟悉getActiveSocket函数导致的潜在问�?请不要省�?参数

### webRpcExternalServerObject.external

```aardio aardio
webRpcExternalServerObject.external = {
    /*可以在这里指定允许chrome访问的对象和函数
在chrome里引用虚拟的"/aardio.js"导入aardio对象即可访问这里的成员函�?
请在调用start函数以前设置此对�?/
}

```

### webRpcExternalServerObject.getActiveSocket()

获取RPC服务端当前活动套接字句柄

,任何触发消息处理、异步套接字处理程序的代码都有可能改变这个函数的返回�?
任何时候都不推荐使用此函数

更好的替代方案是在RPC函数名前添加$字符,用于通知aardio在回调参数中添加$参数

回调$参数可以稳定可靠的获取当前套接字

### webRpcExternalServerObject.getPort()

返回端口�?
### webRpcExternalServerObject.getUrl()

此函数可自动调用 start 函数�?
参数 @1 指定资源文件路径,

转换并返回为可以通过内嵌 HTTP 服务端访问的网址�?
可将此函数获取的 aardio.js 嵌入任意浏览器本地打开的网�?
如果参数 @1 传入小写 http: �?https: 开头的网址�?
则返回了附加 rpcServerPort �?rpcAasdl 参数的网址�?
aardio.js 支持识别这些参数并自动初始化

远程网页如果不指�?rpcAasdl 参数，则在连接成功前只能使用 aardio.xcall 调用本地函数�?
如果不指�?rpcServerPort 参数�?
则必须调�?aardio.open 主动连接本地接口

### webRpcExternalServerObject.http

aardio创建的HTTP服务�?
[返回对象:asynHttpServerObject](../../wsock/tcp/asynHttpServer.html#asynHttpServerObject)

### webRpcExternalServerObject.httpHandler

```aardio aardio
webRpcExternalServerObject.httpHandler["/test.js" ] = function(response,request,session){
    /*自定义HTTP处理程序
键为请求的路�?值为处理函数,
值也可以直接指定响应字符�?/
}

```

### webRpcExternalServerObject.notify($,"method",...)

调用指定chrome函数,但不需要客户端回调反馈,

参数@1指定客户端套接字句柄,

RPC服务端远程回调函数名首字符为$�?

第一个回�?参数即为当前客户端套接字句柄,

除非熟悉getActiveSocket函数导致的潜在问�?请不要省�?参数

### webRpcExternalServerObject.onClose

```aardio aardio
webRpcExternalServerObject.onClose = function($hSocket,err){
    /*一个网页窗口断开连接触发此事�?/
}

```

### webRpcExternalServerObject.onError

```aardio aardio
webRpcExternalServerObject.onError = function($hSocket,err){
    errput(err,"chrome/rpc error");/*自定义RPC错误处理*/
}

```

### webRpcExternalServerObject.onUrlReady

```aardio aardio
webRpcExternalServerObject.onUrlReady = function(hSocket,url){
    /*页面加载完成并且页面上的DOM内容、aardio模块都已准备就绪*/
}

```

### webRpcExternalServerObject.publish(method,...)

主动向所有客户端发送通知

method指定网页客户端方法名,

可添加任意个调用参数

### webRpcExternalServerObject.rpc

aardio创建的JSON-RPC服务�?
[返回对象:websocketjsonserverObject](#websocketjsonserverObject)

### webRpcExternalServerObject.start(端口,IP)

启动 RPC 服务�?

所有参数可�?IP默认�?127.0.0.1,

建议服务端IP保持默认�?127.0.0.1�?
即可在任意网页中调用 aardio.js 并导�?aardio 对象,

可嵌�?HTTPS 网页

### webRpcExternalServerObject.survey(method,...)

发起调查任务,

调用所有网页客户端的同名函�?

method指定客户端方法名,

可添加任意个调用参数

请使用callback函数指定调查结束后客户端回调的函�?
### webRpcExternalServerObject.ws

aardio创建的WebSocket服务�?
[返回对象:websocketserverObject](#websocketserverObject)

### webRpcExternalServerObject.xcall($,"method",...)

调用chrome函数,

参数@1指定客户端套接字句柄,

RPC服务端远程回调函数名首字符为$�?第一个回�?参数即为当前客户端套接字句柄,

除非熟悉getActiveSocket函数导致的潜在问�?请不要省�?参数

在chrome的js代码使用 aardio.on("method")

添加允许aardio调用的js回调函数.

可选使用callback函数指定一个同名回调函数按收本次调用chrome的返回�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/web/rpc/externalServer.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/web/rpc/externalServer.md')

