[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: HTTP/WebSocket/JSON-RPC 三合一体服务端

```aardio aardio
//WS-JSON-RPC服务�?
import win.ui;
/*DSG{{*/
var winform = win.form(text="HTTP/WebSocket/JSON-RPC 三合一体服务端";left=10;top=4;right=774;bottom=467)
winform.add(
btnPublish={cls="button";text="群发通知消息";left=505;top=411;right=621;bottom=450;db=1;dr=1;z=2};
btnSurvey={cls="button";text="发起调查任务";left=633;top=408;right=746;bottom=449;db=1;dr=1;z=3};
txtMessage={cls="edit";left=29;top=22;right=741;bottom=389;db=1;dl=1;dr=1;dt=1;edge=1;multiline=1;z=1}
)
/*}}*/

//创建WebSocket服务�?import web.socket.server;
var wsrv = web.socket.server();

//创建JSON-RPC服务�?import web.socket.jsonServer;
var rpcServer = web.socket.jsonServer(wsrv);

//指定客户端可以调用的对象和方�?rpcServer.external ={

    /*
    如果函数名首字符�?，第一个回调参数为$( 表示当前客户端套接字句柄 )�?    */
    $hello = function($,name){
        return "hello " + name;
    }

    aardio= {

        hello = function(name){
            return "aardio.hello " + name;
        }
    }
}

//客户端使用HTTP请求切换到WebSocket协议
wsrv.onUpgradeToWebsocket = function(hSocket,request,response,protocol,origin){
    if( request.path == "/jsonrpc" ){
        //允许指定的套接字开启JSON-RPC服务
        return rpcServer.start(hSocket);
    }

    //禁止访问其他地址
    response.close();
}

//一个客户端连接过来�?wsrv.onOpen = function(hSocket){
    var client = wsrv.client(hSocket);
    if(client)  winform.txtMessage.print("客户端已连接", client.getRemoteIp() );
    rpcServer.notify(hSocket,"hello","服务端通知");
}

//一个客户端掉线�?wsrv.onClose = function(hSocket){
    winform.txtMessage.print("客户端已断线",hSocket);
}

//一个客户端出错�?wsrv.onError = function(hSocket,err){
    winform.txtMessage.print("出错�?,hSocket,err);
}

//一个客户端发消息过来了
wsrv.onMessage = function(hSocket,msg){
    winform.txtMessage.print(hSocket,msg.data);
    wsrv.send(hSocket,"WebSocket客户端，收到了你发过来的消息�? + msg.data)
}

//启动服务�?if( wsrv.start(,8879) ){
    winform.txtMessage.print( wsrv.getUrl("jsonrpc"),"已启�?WebSocket/JSON-RPC 服务�?);
    winform.txtMessage.print( wsrv.httpServer.getUrl(),"已启�?HTTP服务�?);
}
else {
    winform.txtMessage.print("启动失败，建议修改端口号")
}

//同一个端口还可以同时运行HTTP服务�?wsrv.httpServer.run(
    function(response,request){
         //response.loadcode( request.path  );
         winform.txtMessage.print("HTTP协议访问�?,request.url);

         loadcodex(`
        <!doctype html>
        <html><head></head><body style="white-space:pre"><?
            response.write("欢迎使用HTTP/WebSocket/JSON-RPC 三合一体服务端");
        ?></body>
        </html>`)
    }
);

winform.btnPublish.oncommand = function(id,event){

    //发布订阅模式：在指定频道发布消息，支持传给客户端不定个数的参�?    rpcServer.publish("serverTime",time() )
}

winform.btnSurvey.oncommand = function(id,event){

    //调查模式：对客户端发起问询，支持传给客户端不定个数的参数
    rpcServer.survey("clientTime");

}

rpcServer.xcallback.clientTime = function(hSocket,result,err){
    winform.txtMessage.print( wsrv.getRemoteIp(hSocket) +"返回调查结果:"
        , result );
}

winform.show()
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Web/WebSocket/jsonServer.md)

