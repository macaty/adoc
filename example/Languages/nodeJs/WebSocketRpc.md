[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 创建WebSocket/JSON-RPC 服务端与Node.js交互的例�?
```aardio aardio
//Node.js 通过 JSON-RPC(WebSocket) 调用 aardio
import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio创建WebSocket/JSON-RPC 服务端与Node.js交互的例�?;left=10;top=4;right=774;bottom=467)
winform.add(
txtMessage={cls="edit";left=29;top=22;right=741;bottom=432;db=1;dl=1;dr=1;dt=1;edge=1;multiline=1;z=1}
)
/*}}*/

//创建 WebSocket 服务�?import web.socket.server;
var wsrv = web.socket.server();

//创建 JSON-RPC 服务�?import web.socket.jsonServer;
var rpcServer = web.socket.jsonServer(wsrv);

//这里可以自定义WebSocket 服务端可以使用的 URL 路径
wsrv.onUpgradeToWebsocket = function(hSocket,request,response,protocol,origin){
    return rpcServer.start(hSocket);
}

//指定 node.js 客户端可以调用的对象和方�?rpcServer.external = {

    hello = function(a,b){
        winform.txtMessage.print("node.js调用hello函数,参数�?,a,b);
        return "来自aardio的返回�?" ;
    }

    aardio  = {

        print = function(txt){
            winform.txtMessage.print( txt );
        }
    }
}

//启动 WebSocket 服务�?wsrv.start();

import nodeJs;
nodeJs.startEnviron(
    wsUrl = wsrv.getUrl();//设置node.js的启动参�?)

var js = /***
var startEnviron = require('startEnviron');
var WebSocket = require('rpc-websockets').Client;

var ws = new WebSocket(startEnviron.wsUrl)
ws.on('open', function() {

  ws.call('hello', ['JS传过来的参数1', 'JS传过来的参数2']).then(result=> {

    //也可以支持名字空间，注意调用参数必须放到数组�?    ws.call("aardio.print",[result]).catch(e=>{
        console.log("bm ",e)
    });
  })
})
***/

//自动安装 JS 代码中引用的模块，如果已经安装了模块，这句代码会自动忽略不执�?nodeJs.prequireByJs(winform.txtMessage,js);

//执行JS代码，nodeJs.execLimit 函数会保证在退出时退�?Node 进程
var node = nodeJs.execLimit(js);

//�?Node 进程标准输出重定向到文本框中
node.logResponse(winform.txtMessage);

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/nodeJs/WebSocketRpc.md)

