[aardio 鏂囨。](../../../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 璋冪敤 Python 鍒涘缓 JSON RPC 瀹㈡埛绔?
```aardio aardio
//aardio 璋冪敤 Python 鍒涘缓 JSON RPC 瀹㈡埛绔?import py3;
import py3.lib.jsonrpclib;//杩欎釜鎵╁睍搴撴槸鑷姩瀹夎 Python 鎵╁睍妯″潡鐨勪竴涓紨绀?
//鍚姩 aardio 瀹炵幇鐨?JSON RPC 鏈嶅姟绔?thread.create("~/example/Web/JSON/rpcServer.aardio")
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

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python 3.x/JSON-RPC/http-client.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python 3.x/JSON-RPC/http-client.md')

