[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: WebSocket客户端演�?
```aardio aardio
//异步客户�?
import win.ui;
/*DSG{{*/
var winform = win.form(text="WebSocket客户端演�?;right=770;bottom=467)
winform.add(
btnClose={cls="button";text="断开";left=556;top=293;right=710;bottom=331;db=1;dr=1;z=6};
btnOpen={cls="button";text="连接WebSocket服务�?;left=381;top=293;right=535;bottom=331;db=1;dr=1;z=2};
btnSend={cls="button";text="发送数�?;left=569;top=346;right=711;bottom=426;db=1;dr=1;z=4};
txtMessage={cls="edit";left=29;top=22;right=741;bottom=285;db=1;dl=1;dr=1;dt=1;edge=1;multiline=1;z=1};
txtSend={cls="edit";text="WebSocket测试";left=29;top=348;right=558;bottom=423;db=1;dl=1;dr=1;edge=1;multiline=1;z=3};
txtUrl={cls="edit";text="ws://localhost:8876/aardio";left=29;top=295;right=368;bottom=331;db=1;dl=1;dr=1;edge=1;z=5}
)
/*}}*/

import web.socket.client;
var ws = web.socket.client();

ws.onOpen = function(){
    ws.send("服务端你好吗？！")
}

ws.onClose = function(event){
    winform.txtMessage.print("onClose",event);
}

ws.onError = function(err){
    winform.txtMessage.print("onError",err);
}

ws.onMessage = function(msg){
    winform.txtMessage.print(msg.data);
}

winform.btnSend.oncommand = function(id,event){
    ws.send(winform.txtSend.text)
}

winform.btnOpen.oncommand = function(id,event){
    ws.connect(winform.txtUrl.text);
}

winform.btnClose.oncommand = function(id,event){
    ws.close();
}

winform.txtUrl.text = "ws://localhost:8876/aardio";
ws.originUrl = "http://localhost:8876";

winform.show()
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Web/WebSocket/client.md)

