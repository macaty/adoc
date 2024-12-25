[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: HTTP-JSON-RPC 客户�?
```aardio aardio
//HTTP-JSON-RPC 客户�?
import console;
import web.rpc.jsonClient;

//创建JSON-RPC 2.0客户�?var client = web.rpc.jsonClient("http://127.0.0.1:8610/jsonrpc");

//调用远程对象和函�?aardio.$hello
var rep,err = client.aardio.$hello("jacen" );

//返回对象的格式参�? http://www.jsonrpc.org/specification
if( rep[["result"]] ){
    console.dump( rep.result );
}
elseif( err ){
    /*
    本地错误�?err 为错误信息，
    服务端错误则 err �?rep[["error"]] 对象�?JSON 文本格式
    */
    console.dump(err);
}

console.pause(true);

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Web/JSON/rpcClient.md)

