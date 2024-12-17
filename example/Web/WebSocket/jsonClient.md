[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: WebSocket/JSON-RPC 2.0瀹㈡埛绔?
```aardio aardio
//WS-JSON-RPC瀹㈡埛绔?import win.ui;
/*DSG{{*/
var winform = win.form(text="WebSocket/JSON-RPC 2.0瀹㈡埛绔?;right=770;bottom=467)
winform.add(
btnConnect={cls="button";text="杩炴帴WebSocket/JSON-RPC 2.0鏈嶅姟绔?;left=456;top=414;right=737;bottom=459;db=1;dr=1;z=3};
txtMessage={cls="edit";left=29;top=22;right=741;bottom=409;db=1;dl=1;dr=1;dt=1;edge=1;multiline=1;z=1};
txtUrl={cls="edit";text="ws://localhost:8879/jsonrpc";left=32;top=418;right=450;bottom=457;db=1;dl=1;dr=1;edge=1;z=2}
)
/*}}*/

import web.socket.jsonClient;
var ws = web.socket.jsonClient();

//鐩戝惉鏈嶅姟绔簨浠?ws.on("hello",function(param){
    winform.txtMessage.print("鏉ヨ嚜鏈嶅姟绔殑娑堟伅锛?,param );
})

//鎵撳紑杩炴帴瑙﹀彂鐨勪簨浠?ws.on("open",function(){
    ws.$hello("浣犲ソ鍚?).end = function(result,err){
        winform.txtMessage.print(result,err)
    }

})

ws.on("close",function(){
    winform.txtMessage.print("宸插叧闂繛鎺?)
});

ws.on("error",function(err){
    winform.txtMessage.print("鍑洪敊浜?,err);
});

//鍙戝竷璁㈤槄妯″紡锛氳闃呮湇鍔″櫒鐨勬寚瀹氶閬?鏀寔鎺ユ敹涓嶅畾涓暟鐨勫弬鏁?ws.on("serverTime",function(param){
    winform.txtMessage.print("鏈嶅姟绔彂甯冧簡褰撳墠鏃堕棿锛?,param );
});

//璋冩煡妯″紡锛氬簲绛旀湇鍔″櫒鎻愬嚭鐨勮皟鏌ヤ换鍔?鏀寔鎺ユ敹涓嶅畾涓暟鐨勫弬鏁?ws.on("clientTime",function(){
    return time()
});

//杩炴帴chrome
winform.btnConnect.oncommand = function(id,event){
    ws.connect(winform.txtUrl.text);
}

winform.show()
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Web/WebSocket/jsonClient.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Web/WebSocket/jsonClient.md')

