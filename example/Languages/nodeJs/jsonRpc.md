[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 通过 JSON-RPC(HTTP) 调用 Node.js

```aardio aardio
//aardio 通过 JSON-RPC(HTTP) 调用 Node.js
import nodeJs;

//自动安装node.js模块
nodeJs.require('jayson');

var js = /***
var startEnviron = require('startEnviron')
var jayson = require('jayson')

//创建服务�?var server = jayson.server({
  brest: function (args, callback) {
    callback(null, startEnviron)
    listener.close() ;
  }
})

//启动服务�?var listener = server.http().listen(startEnviron.port);
***/

//运行JS代码创建 RPC 服务端，nodeJs.execLimit 函数会保证在退出时退�?Node 进程
var node = nodeJs.execLimit(js);

import console;
import web.rpc.jsonClient;
var jsonRpc = web.rpc.jsonClient("http://localhost:" + nodeJs.port);

//使用aardio调用node.js函数
var jsonData = jsonRpc.brest("admin","123123");

//显示node.js返回�?if( jsonData.result ){
    console.dump( jsonData.result );
}
else {
    console.dump( jsonData.error.message );
}

console.pause(true);

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/nodeJs/jsonRpc.md)

