[aardio 文档](../../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 Python 创建 JSON RPC 客户�?
```aardio aardio
//aardio 调用 Python 创建 JSON RPC 客户�?import py3;
import py3.lib.jsonrpclib;//这个扩展库是自动安装 Python 扩展模块的一个演�?
//启动 aardio 实现�?JSON RPC 服务�?thread.create("~/example/Web/JSON/rpcServer.aardio")
thread.delay(1000);

var pyCode = /**
def testRpc():
    import jsonrpclib
    server = jsonrpclib.Server('http://127.0.0.1:8610/jsonrpc')
    return server.hello("jacen" )
**/

py3.exec(pyCode);

import console;
console.log( py3.main.testRpc() )
console.pause()

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python 3.x/JSON-RPC/http-client.md)

