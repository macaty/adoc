[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: web.rest 支持服务端流式输�?
```aardio aardio
//web.rest 支持服务端流式输�?import win.ui;
/*DSG{{*/
var winform = win.form(text="web.rest - 服务端推送事�?;right=753;bottom=434)
winform.add(
edit={cls="edit";left=20;top=12;right=734;bottom=404;edge=1;multiline=1;z=1}
)
/*}}*/

/*
web.rest 客户端支�?SSE( Server-Sent Events) 事件流（ MIME �?"text/event-stream" ），
同时自动兼容 ndjson 流（ MIME �?"application/x-ndjson" ）�?*/

import wsock.tcp.simpleHttpServer;
var url = wsock.tcp.simpleHttpServer.startUrl(function(response,request,session){

    while (true) {
        response.eventStream(
            event = "ping";
            data = { time = time() };
        )

        sleep(1000);
    }

    /*
    //推�?ndjson �?    response.contentType = "application/x-ndjson";
    while (true) {
        response.write( { time = time() },'\n' )
        sleep(1000);
    }
    */
})

thread.invoke(
    function(url,winform){
        import web.rest.jsonLiteClient;
        var http = web.rest.jsonLiteClient();

        var eventSource = http.api(url)

        //参数 @2 �?参数@3 指定接收数据回调函数则自动支�?SSE，兼�?ndjson 流�?        eventSource.get( , function(message){
            //注意这里�?message 已经�?JSON 解析为单个对�?            winform.edit.print("HTTP 服务端推送了事件",type(message))
            winform.edit.print(message);
        } )

    },url,winform
)

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Web/REST/sse.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Web/REST/sse.md')

