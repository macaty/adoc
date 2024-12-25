[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 虚拟文件路径

```aardio aardio
//虚拟文件路径
import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio form";right=759;bottom=469)
winform.add()
/*}}*/

import wsock.tcp.asynHttpServer;
var httpServer = wsock.tcp.asynHttpServer();

/*
asynHttpServer 可以极简单地在内存虚拟文件地址,
写扩展库的时候利用这功能可以避免引用外部文件（请参�?com.cube3 扩展库的源码）�?*/
httpServer.run( {

    //自定义某个路径返回的数据
    ["/index.html"] = "hello"; //这里也可以用 $"文件路径" 将文件内容编译到一个字符串�?
    //自定义某个路径的响应程序
    ["/hello"] = function(response,request,session){
         response.loadcode(request.path);
    }

    //表里找不到的路径，仍然会正常访问存在的文件（支持资源文件�?} );

//这里可以指定 IP 和端口，不指定则自动分配空闲端口
httpServer.start("127.0.0.1");

//可以支持 aardio 服务�?HTML 模板语法
var url = httpServer.getUrl("/index.html"); //参数支持 aardio 工程嵌入资源目录路径

import web.form;
var wb = web.form(winform);

//用浏览器组件打开网页试试
wb.go(url);

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Web/HTTPServer/asynHttpServer.table.md)

