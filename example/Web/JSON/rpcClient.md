[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: HTTP-JSON-RPC 瀹㈡埛绔?
```aardio aardio
//HTTP-JSON-RPC 瀹㈡埛绔?
import console;
import web.rpc.jsonClient;

//鍒涘缓JSON-RPC 2.0瀹㈡埛绔?var client = web.rpc.jsonClient("http://127.0.0.1:8610/jsonrpc");

//璋冪敤杩滅▼瀵硅薄鍜屽嚱鏁?aardio.$hello
var rep,err = client.aardio.$hello("jacen" );

//杩斿洖瀵硅薄鐨勬牸寮忓弬鑰? http://www.jsonrpc.org/specification
if( rep[["result"]] ){
    console.dump( rep.result );
}
elseif( err ){
    /*
    鏈湴閿欒鍒?err 涓洪敊璇俊鎭紝
    鏈嶅姟绔敊璇垯 err 涓?rep[["error"]] 瀵硅薄鐨?JSON 鏂囨湰鏍煎紡
    */
    console.dump(err);
}

console.pause(true);

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Web/JSON/rpcClient.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Web/JSON/rpcClient.md')

