[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: WebSocket瀹㈡埛绔紨绀?
```aardio aardio
//寮傛瀹㈡埛绔?
import win.ui;
/*DSG{{*/
var winform = win.form(text="WebSocket瀹㈡埛绔紨绀?;right=770;bottom=467)
winform.add(
btnClose={cls="button";text="鏂紑";left=556;top=293;right=710;bottom=331;db=1;dr=1;z=6};
btnOpen={cls="button";text="杩炴帴WebSocket鏈嶅姟绔?;left=381;top=293;right=535;bottom=331;db=1;dr=1;z=2};
btnSend={cls="button";text="鍙戦�佹暟鎹?;left=569;top=346;right=711;bottom=426;db=1;dr=1;z=4};
txtMessage={cls="edit";left=29;top=22;right=741;bottom=285;db=1;dl=1;dr=1;dt=1;edge=1;multiline=1;z=1};
txtSend={cls="edit";text="WebSocket娴嬭瘯";left=29;top=348;right=558;bottom=423;db=1;dl=1;dr=1;edge=1;multiline=1;z=3};
txtUrl={cls="edit";text="ws://localhost:8876/aardio";left=29;top=295;right=368;bottom=331;db=1;dl=1;dr=1;edge=1;z=5}
)
/*}}*/

import web.socket.client;
var ws = web.socket.client();

ws.onOpen = function(){
    ws.send("鏈嶅姟绔綘濂藉悧锛燂紒")
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

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Web/WebSocket/client.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Web/WebSocket/client.md')

