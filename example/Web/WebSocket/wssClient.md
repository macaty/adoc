[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: WebSocket 异步客户端（ WSS 客户端）

```aardio aardio
//WebSocket 异步客户端（ WSS 客户端）
import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio form";right=759;bottom=469)
winform.add(
edit={cls="edit";left=25;top=21;right=733;bottom=424;edge=1;multiline=1;z=1}
)
/*}}*/

//异步客户端只能用于界面线�?import web.SocketSharp;

//此客户端支持 wss 协议
var ws = web.SocketSharp.WebSocket ("wss://websocket-echo.com");

//自定�?HTTP �?ws.Headers["User-Agent"] = "my-websocket";

ws.OnOpen = function(sender, e){
    ws.Send("发送消�?);
}

ws.OnClose = function(sender, e){
    winform.edit.print("已关闭连�?,e.Reason);
}

ws.OnError = function(sender, e){
    winform.edit.print(e.Message);
}

ws.OnMessage = function(sender, e){
    winform.edit.print("收到服务端消�?",e.Data);
}

//异步连接服务�?ws.ConnectAsync();

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Web/WebSocket/wssClient.md)

