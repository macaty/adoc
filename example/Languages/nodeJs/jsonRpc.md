[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 閫氳繃 JSON-RPC(HTTP) 璋冪敤 Node.js

```aardio aardio
//aardio 閫氳繃 JSON-RPC(HTTP) 璋冪敤 Node.js
import nodeJs;

//鑷姩瀹夎node.js妯″潡
nodeJs.require('jayson');

var js = /***
var startEnviron = require('startEnviron')
var jayson = require('jayson')

//鍒涘缓鏈嶅姟绔?var server = jayson.server({
  brest: function (args, callback) {
    callback(null, startEnviron)
    listener.close() ;
  }
})

//鍚姩鏈嶅姟绔?var listener = server.http().listen(startEnviron.port);
***/

//杩愯JS浠ｇ爜鍒涘缓 RPC 鏈嶅姟绔紝nodeJs.execLimit 鍑芥暟浼氫繚璇佸湪閫�鍑烘椂閫�鍑?Node 杩涚▼
var node = nodeJs.execLimit(js);

import console;
import web.rpc.jsonClient;
var jsonRpc = web.rpc.jsonClient("http://localhost:" + nodeJs.port);

//浣跨敤aardio璋冪敤node.js鍑芥暟
var jsonData = jsonRpc.brest("admin","123123");

//鏄剧ずnode.js杩斿洖鍊?if( jsonData.result ){
    console.dump( jsonData.result );
}
else {
    console.dump( jsonData.error.message );
}

console.pause(true);

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/nodeJs/jsonRpc.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/nodeJs/jsonRpc.md')

