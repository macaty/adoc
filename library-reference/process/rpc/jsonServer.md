[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# process.rpc.jsonServer 库模块帮助文�?
## process.rpc 成员列表

### process.rpc.jsonServer

基于进程管道实现�?JSON-RPC 2.0 服务端，

对应的客户端实现�?process.rpc.jsonClient �?
规则如下�?
1、客户端不应当向服务端发送任何不符合 JSON-RPC 规范的内容�?
2、客户端应当仅将包含 jsonrpc 字段的对象解析为 JSON-RPC 响应对象�?
在批量调用时，应当仅将包含上述对象的非空数组解析�?JSON-RPC 响应对象�?
客户端应当允许服务端进程的存在其他输出或错误输出�?
3、服务端在发送每�?JSON-RPC 响应对象不会包含换行且在尾部添加换行�?

'�?
[关于JSON-RPC 2.0](http://www.jsonrpc.org/specification)

### process.rpc.jsonServer()

创建 JSON-RPC 2.0 服务�?
可选在构造参数中指定监听客户端调用的监听器对�?
如果不指定参�?保用对象自身监听客户端调�?
[返回对象:processRpcJsonServerObject](#processRpcJsonServerObject)

## processRpcJsonServerObject 成员列表

### processRpcJsonServerObject.?

客户端可以调用的远程对象名或远程方法名字,

客户端传过来的params参数必须是数�?
服务端会展开此数组作为函数的调用参数

函数第一个返回值指定为客户端获取的result返回�?
函数的第二个返回值指定为客户端error错误对象

错误对象可以是数值，字符串、或符合JSON-RPC2.0协议的表对象,

[返回对象:webRpcJsonClientObject](https://www.aardio.com/zh-cn/doc/library-reference/web/rpc/jsonClient.html#webRpcJsonClientObject)

## processRpcJsonServerObject.rpc 成员列表

### processRpcJsonServerObject.rpc.aasdl

指定自定义的aasdl

如果不指�?服务端会根据external自动生成aasdl

如果客户端请求的方法名为"?"�?返回此属�?

[关于aasdl](https://github.com/aardio/aardio-js/blob/master/AASDL.md)

### processRpcJsonServerObject.rpc.afterJsonStringify

```aardio aardio
processRpcJsonServerObject.rpc.afterJsonStringify = function(jsonData){
    /*可以在这里加密服务端JSON,返回null中止本次调用*/
    return jsonData;
}

```

### processRpcJsonServerObject.rpc.beforeJsonParse

```aardio aardio
processRpcJsonServerObject.rpc.beforeJsonParse = function(jsonData){
    /*可以在这里解密客户端数据,返回null中止本次调用*/
    return jsonData;
}

```

### processRpcJsonServerObject.rpc.external

指定包含客户端可以调用的远程函数的表对象,可嵌套子�?

如果创建服务端对象的构造参数中没有指定�?

这个对象默认指向对象自身

可在调用run函数之前更改此对�?
### processRpcJsonServerObject.rpc.onError

```aardio aardio
processRpcJsonServerObject.rpc.onError = function(err,requestData){
    /*服务器内部错误时触发此事�?err为抛出的异常对象,一般为错误信息
requestData为客户端发送的请求数据*/
}

```

### processRpcJsonServerObject.rpc.run()

运行JSON-RPC服务端响应用户请�?
### 自动完成常量

\_JSONRPC\_INTERNAL\_ERROR=-32603

\_JSONRPC\_INVALID\_PARAMS=-32602

\_JSONRPC\_INVALID\_REQUEST=-32600

\_JSONRPC\_METHOD\_NOTFOUND=-32601

\_JSONRPC\_PARSE\_ERROR=-32700

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/process/rpc/jsonServer.md)

