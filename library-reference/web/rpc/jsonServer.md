[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# web.rpc.jsonServer 库模块帮助文�?
## web.rpc 成员列表

### web.rpc.jsonServer

基于HTTP协议的JSON-RPC 2.0服务�?
需要在HTTP服务器上运行

[关于JSON-RPC 2.0](javascript:if(confirm('http://www.jsonrpc.org/specification  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ����һ������·���ⲿ������Ϊ������ʼ��ַ�ĵ�ַ��  \n\n�����ڷ������ϴ�����?'))window.location='http://www.jsonrpc.org/specification')

### web.rpc.jsonServer()

创建JSON-RPC 2.0服务�?
可选在构造参数中指定监听客户端调用的监听器对�?
如果不指定参�?保用对象自身监听客户端调�?
[返回对象:webrpcjsonServerObject](#webrpcjsonServerObject)

## webrpcjsonServerObject 成员列表

### webrpcjsonServerObject.?

客户端可以调用的远程对象名或远程方法名字,

客户端传过来的params参数必须是数�?
服务端会展开此数组作为函数的调用参数

函数第一个返回值指定为客户端获取的result返回�?
函数的第二个返回值指定为客户端error错误对象

错误对象可以是数值，字符串、或符合JSON-RPC2.0协议的表对象,

[返回对象:webRpcJsonClientObject](jsonClient.html#webRpcJsonClientObject)

## webrpcjsonServerObject.rpc 成员列表

### webrpcjsonServerObject.rpc.aasdl

指定自定义的aasdl

如果不指�?服务端会根据external自动生成aasdl

如果客户端请求的方法名为"?"�?返回此属�?

[关于aasdl](javascript:if(confirm('https://github.com/aardio/aardio-js/blob/master/AASDL.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ����һ������·���ⲿ������Ϊ������ʼ��ַ�ĵ�ַ��  \n\n�����ڷ������ϴ�����?'))window.location='https://github.com/aardio/aardio-js/blob/master/AASDL.md')

### webrpcjsonServerObject.rpc.afterJsonStringify

```aardio aardio
webrpcjsonServerObject.rpc.afterJsonStringify = function(jsonData){
    /*可以在这里加密服务端JSON,返回null中止本次调用*/
    return jsonData;
}

```

### webrpcjsonServerObject.rpc.beforeJsonParse

```aardio aardio
webrpcjsonServerObject.rpc.beforeJsonParse = function(jsonData){
    /*可以在这里解密客户端数据,返回null中止本次调用*/
    return jsonData;
}

```

### webrpcjsonServerObject.rpc.external

指定包含客户端可以调用的远程函数的表对象,可嵌套子�?
如果远程函数名第一个字符是$,则第一个回调参数为$,$对象由run函数指定,

如果创建服务端对象的构造参数中没有指定�?

这个对象默认指向对象自身

可在调用run函数之前更改此对�?
### webrpcjsonServerObject.rpc.onError

```aardio aardio
webrpcjsonServerObject.rpc.onError = function(err,requestData){
    /*服务器内部错误时触发此事�?err为抛出的异常对象,一般为错误信息
requestData为客户端发送的请求数据*/
}

```

### webrpcjsonServerObject.rpc.run()

运行JSON-RPC服务端响应用户请�?
可选在函数参数中所有名字首字符�?的回调函数的首个回调$参数,

$参数默认为request

### 自动完成常量

\_JSONRPC\_INTERNAL\_ERROR=-32603

\_JSONRPC\_INVALID\_PARAMS=-32602

\_JSONRPC\_INVALID\_REQUEST=-32600

\_JSONRPC\_METHOD\_NOTFOUND=-32601

\_JSONRPC\_PARSE\_ERROR=-32700

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/web/rpc/jsonServer.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/web/rpc/jsonServer.md')

