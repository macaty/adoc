[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 澶氱嚎绋嬫湇鍔″櫒 / 鎺у埗鍙?
```aardio aardio
//澶氱嚎绋嬫湇鍔″櫒 / 鎺у埗鍙?import console;
import process;

import wsock.tcp.simpleHttpServer;
var server = wsock.tcp.simpleHttpServer("127.0.0.1",/*8081*/);

console.log( server.getUrl() )
process.execute( server.getUrl() );

//濡傛灉涓嶉渶瑕佺獥鍙ｇ晫闈紝閭ｄ篃鍙互鐩存帴浣跨敤 wsock.tcp.simpleHttpServer
server.run(
    function(response,request,session){
        if( io.exist( request.path,0)
            && request.path!="/main.aardio" ){
            response.loadcode( request.path )
        }
        else{
            loadcodex(`
        <!doctype html>
        <html><head></head><body style="white-space:pre"><?
            response.jsonPrettyPrint = true;//杈撳嚭缂╄繘鏍煎紡鍖栫殑JSON
            response.write(request);
        ?></body>
        </html>`)

        }
    }
)

/*
import web.rest.client;
var http = web.rest.client();
http.setAuth( "鐢ㄦ埛鍚?, "瀵嗙爜" );
http.get( "http://ddns.oray.com/ph/update",{ hostname = "****.xicp.net" } );

jQuery Ajax 璺ㄥ煙璋冪敤鏂规硶,鍙疄鐜版祻瑙堝櫒涓庢湰鍦板簲鐢ㄤ氦浜?$.ajax({
    type: "get",
    dataType: "text",
    async:false,
    crossDomain: true, //搴旂敤CORS璺ㄥ煙鏈哄埗,蹇呴』璁剧疆Access-Control-Allow-Origin澶?涓嶉�傚悎IE浣庣増鏈?    url:"http://localhost:8081",
    success: function(msg){
        alert( msg.message );
    },
    error: function (XMLHttpRequest, textStatus, errorThrown) {
        alert(errorThrown); //crossDomain: true,async:false, 鎵嶈兘鎹曡幏缃戠粶閿欒
    }

} );
*/

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Web/HTTPServer/simpleHttpServer.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Web/HTTPServer/simpleHttpServer.md')

