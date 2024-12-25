[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: WSS 服务�?
```aardio aardio
//WSS 服务�?import win.ui;
/*DSG{{*/
var winform = win.form(text="wss 服务�?;right=759;bottom=469)
winform.add(
edit={cls="edit";left=12;top=13;right=744;bottom=448;edge=1;multiline=1;z=1}
)
/*}}*/

import console;
import web.SocketSharp;//打开控制台可查看服务端错误输�?
//加载 SSL 证书后可改为 wss:// �?var wssv = web.SocketSharp.Server.WebSocketServer("wss://localhost:8877")

//生成测试证书，ws 协议不需�?import web.SocketSharp.Pfx;
wssv.SslConfiguration.ServerCertificate = System.Security.Cryptography.X509Certificates.X509Certificate2(
    web.SocketSharp.Pfx("/test.pfx","123456")
);

/*
第二个参数用于定义一�?WebSocket 会话类�?每次创建新的 WebSocket 连接时会调用类创建WebSocket 会话实例�?*/
wssv.AddWebSocketService("/echo",class {

    onMessage = function(e){
        /*
        this.socket 会自动绑定为 WebSocketSharp.Server.WebSocketBehavior 实例�?        用法请参�?WebSocketSharp 文档�?
        必须定义 this.onMessage 事件用于接收消息�?        可选定�?this.onOpen, this.onClose, this.onError 事件�?        这几个事件与 WebSocketSharp.Server.WebSocketBehavio 的同名事件用法相同�?        唯一不同的是首字母小写�?
        this.send() 等价于调�?this.socket.Send()
        this.sendAsync() 等价于调�?this.socket.SendAsync()
        唯一区别是首字母小写�?        */

        winform.edit.print("服务端收到消�?,e.data)

        //同步发送，群发�?this.broadcast
        this.send("你好我是服务�?)

        //异步发送，成功回调参数 @2，异步群发用 broadcastAsync
        this.sendAsync("你好我是服务�?,function(completed){

        } )
    }
});

//启动服务�?wssv.Start();

winform.onDestroy = function(){
    wssv.Stop();//关闭服务器，不然下次启动，短时间内端口会是占用状�?}

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Web/WebSocket/wssServer.md)

