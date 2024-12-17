[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鍗曠嚎绋嬪紓姝ユ湇鍔″櫒

```aardio aardio
//鍗曠嚎绋嬪紓姝ユ湇鍔″櫒
import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio form";right=759;bottom=469)
winform.add()
/*}}*/

/*
鍗曠嚎绋嬪紓姝ユ湇鍔″櫒鐢ㄤ簬鐣岄潰绾跨▼锛?涓嶉渶瑕佸垱寤哄绾跨▼锛屽彲浠ュ湪淇濇寔鐣岄潰娑堟伅寰幆鐨勫悓鏃跺搷搴?HTTP 璇锋眰銆?骞朵笖鍩轰簬 wsock.tcp.asynHttpServer 鐨?web.socket.server 鍙湪鍚屼竴绔彛鍚姩 WebSocket 鏈嶅姟銆?*/
import wsock.tcp.asynHttpServer;
var httpServer = wsock.tcp.asynHttpServer();

//杩欓噷鍙互鎸囧畾 IP 鍜岀鍙ｏ紝涓嶆寚瀹氬垯鑷姩鍒嗛厤绌洪棽绔彛
httpServer.start("127.0.0.1");

//鏈嶅姟绔?aardio 鏀寔妯℃澘璇硶锛?https://www.aardio.com/zh-cn/doc/language-reference/templating/syntax.html
var url = httpServer.getUrl("/.www/main.aardio"); //鍙傛暟鏀寔 aardio 宸ョ▼宓屽叆璧勬簮鐩綍璺緞

import web.form;
var wb = web.form(winform);

//鐢ㄦ祻瑙堝櫒缁勪欢鎵撳紑缃戦〉璇曡瘯
wb.go(url);

winform.show();
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Web/HTTPServer/asynHttpServer.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Web/HTTPServer/asynHttpServer.md')

