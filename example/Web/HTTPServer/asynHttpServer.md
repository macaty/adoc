[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 单线程异步服务器

```aardio aardio
//单线程异步服务器
import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio form";right=759;bottom=469)
winform.add()
/*}}*/

/*
单线程异步服务器用于界面线程�?不需要创建多线程，可以在保持界面消息循环的同时响�?HTTP 请求�?并且基于 wsock.tcp.asynHttpServer �?web.socket.server 可在同一端口启动 WebSocket 服务�?*/
import wsock.tcp.asynHttpServer;
var httpServer = wsock.tcp.asynHttpServer();

//这里可以指定 IP 和端口，不指定则自动分配空闲端口
httpServer.start("127.0.0.1");

//服务�?aardio 支持模板语法�?https://www.aardio.com/zh-cn/doc/language-reference/templating/syntax.html
var url = httpServer.getUrl("/.www/main.aardio"); //参数支持 aardio 工程嵌入资源目录路径

import web.form;
var wb = web.form(winform);

//用浏览器组件打开网页试试
wb.go(url);

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Web/HTTPServer/asynHttpServer.md)

