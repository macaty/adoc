[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 多线程服务器 / 控制�?
```aardio aardio
//多线程服务器 / 控制�?import console;
import process;

import wsock.tcp.simpleHttpServer;
var server = wsock.tcp.simpleHttpServer("127.0.0.1",/*8081*/);

console.log( server.getUrl() )
process.execute( server.getUrl() );

//如果不需要窗口界面，那也可以直接使用 wsock.tcp.simpleHttpServer
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
            response.jsonPrettyPrint = true;//输出缩进格式化的JSON
            response.write(request);
        ?></body>
        </html>`)

        }
    }
)

/*
import web.rest.client;
var http = web.rest.client();
http.setAuth( "用户�?, "密码" );
http.get( "http://ddns.oray.com/ph/update",{ hostname = "****.xicp.net" } );

jQuery Ajax 跨域调用方法,可实现浏览器与本地应用交�?$.ajax({
    type: "get",
    dataType: "text",
    async:false,
    crossDomain: true, //应用CORS跨域机制,必须设置Access-Control-Allow-Origin�?不适合IE低版�?    url:"http://localhost:8081",
    success: function(msg){
        alert( msg.message );
    },
    error: function (XMLHttpRequest, textStatus, errorThrown) {
        alert(errorThrown); //crossDomain: true,async:false, 才能捕获网络错误
    }

} );
*/

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Web/HTTPServer/simpleHttpServer.md)

