[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: WebSocket 异步服务端（ WSS 服务端）

```aardio aardio
//WebSocket 异步服务端（ WSS 服务端）

import win.ui;
/*DSG{{*/
var winform = win.form(text="WebSocket单线程异步服务端演示";left=10;top=4;right=774;bottom=467)
winform.add(
txtMessage={cls="edit";left=29;top=22;right=741;bottom=432;db=1;dl=1;dr=1;dt=1;edge=1;multiline=1;z=1}
)
/*}}*/

import web.socket.server;
var wsrv = web.socket.server();

//客户端使用HTTP请求切换到WebSocket协议
wsrv.onUpgradeToWebsocket = function(hSocket,request,response,protocol,origin){
    if( request.path!="/aardio"){
        //关闭应答即可拒绝请求 调用response.close()也可�?        return response.errorStatus(404);
    }
}

//一个客户端连接过来�?wsrv.onOpen = function(hSocket){
    var client = wsrv.client(hSocket);
    if(client)  winform.txtMessage.print( client.getRemoteIp() );
    wsrv.send(hSocket,"WebSocket客户端你好！")
}

//一个客户端掉线�?wsrv.onClose = function(hSocket,event){
    winform.txtMessage.print("onClose",hSocket,event);
}

//一个客户端出错�?wsrv.onError = function(hSocket,err){
    winform.txtMessage.print("onError",hSocket,err);
}

//一个客户端发消息过来了
wsrv.onMessage = function(hSocket,msg){
    winform.txtMessage.print(hSocket,msg.data);
    wsrv.send(hSocket,"WebSocket客户端，收到了你发过来的消息�? + msg.data)
}

//启动服务�?if( wsrv.start(,8876) ){
    winform.txtMessage.print( wsrv.getUrl() + "/aardio","已启动WebSocket服务�?);
    winform.txtMessage.print( wsrv.httpServer.getUrl(),"已启动HTTP服务�?);
}
else {
    winform.txtMessage.print("启动失败，建议修改端口号")
}

//同一个端口还可以同时运行HTTP服务�?wsrv.httpServer.run(
    function(response,request){
         //winform.txtMessage.print( request );
         winform.txtMessage.print("HTTP协议访问�?,request.url);

         response.contentType = "text/json"
         response.jsonPrettyPrint = true;
         response.write(request)
    }
);

winform.show()
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Web/WebSocket/server.md)

