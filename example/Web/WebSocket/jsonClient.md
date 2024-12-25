[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: WebSocket/JSON-RPC 2.0客户�?
```aardio aardio
//WS-JSON-RPC客户�?import win.ui;
/*DSG{{*/
var winform = win.form(text="WebSocket/JSON-RPC 2.0客户�?;right=770;bottom=467)
winform.add(
btnConnect={cls="button";text="连接WebSocket/JSON-RPC 2.0服务�?;left=456;top=414;right=737;bottom=459;db=1;dr=1;z=3};
txtMessage={cls="edit";left=29;top=22;right=741;bottom=409;db=1;dl=1;dr=1;dt=1;edge=1;multiline=1;z=1};
txtUrl={cls="edit";text="ws://localhost:8879/jsonrpc";left=32;top=418;right=450;bottom=457;db=1;dl=1;dr=1;edge=1;z=2}
)
/*}}*/

import web.socket.jsonClient;
var ws = web.socket.jsonClient();

//监听服务端事�?ws.on("hello",function(param){
    winform.txtMessage.print("来自服务端的消息�?,param );
})

//打开连接触发的事�?ws.on("open",function(){
    ws.$hello("你好�?).end = function(result,err){
        winform.txtMessage.print(result,err)
    }

})

ws.on("close",function(){
    winform.txtMessage.print("已关闭连�?)
});

ws.on("error",function(err){
    winform.txtMessage.print("出错�?,err);
});

//发布订阅模式：订阅服务器的指定频�?支持接收不定个数的参�?ws.on("serverTime",function(param){
    winform.txtMessage.print("服务端发布了当前时间�?,param );
});

//调查模式：应答服务器提出的调查任�?支持接收不定个数的参�?ws.on("clientTime",function(){
    return time()
});

//连接chrome
winform.btnConnect.oncommand = function(id,event){
    ws.connect(winform.txtUrl.text);
}

winform.show()
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Web/WebSocket/jsonClient.md)

