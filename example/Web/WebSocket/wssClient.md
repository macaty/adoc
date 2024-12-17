[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: WebSocket 寮傛瀹㈡埛绔紙 WSS 瀹㈡埛绔級

```aardio aardio
//WebSocket 寮傛瀹㈡埛绔紙 WSS 瀹㈡埛绔級
import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio form";right=759;bottom=469)
winform.add(
edit={cls="edit";left=25;top=21;right=733;bottom=424;edge=1;multiline=1;z=1}
)
/*}}*/

//寮傛瀹㈡埛绔彧鑳界敤浜庣晫闈㈢嚎绋?import web.SocketSharp;

//姝ゅ鎴风鏀寔 wss 鍗忚
var ws = web.SocketSharp.WebSocket ("wss://websocket-echo.com");

//鑷畾涔?HTTP 澶?ws.Headers["User-Agent"] = "my-websocket";

ws.OnOpen = function(sender, e){
    ws.Send("鍙戦�佹秷鎭?);
}

ws.OnClose = function(sender, e){
    winform.edit.print("宸插叧闂繛鎺?,e.Reason);
}

ws.OnError = function(sender, e){
    winform.edit.print(e.Message);
}

ws.OnMessage = function(sender, e){
    winform.edit.print("鏀跺埌鏈嶅姟绔秷鎭?",e.Data);
}

//寮傛杩炴帴鏈嶅姟绔?ws.ConnectAsync();

winform.show();
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Web/WebSocket/wssClient.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Web/WebSocket/wssClient.md')

