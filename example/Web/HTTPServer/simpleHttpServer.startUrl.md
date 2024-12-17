[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 最简多线程服务端

```aardio aardio
//最简多线程服务端
import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio form";right=759;bottom=469)
winform.add()
/*}}*/

import wsock.tcp.simpleHttpServer;
/*
wsock.tcp.simpleHttpServer 用于创建多线�?HTTP 服务器�?默认的服务器线程是阻塞的，所以不要在窗口界面线程启动服务器线程�?
wsock.tcp.simpleHttpServer.mainThread 则用于界面线程创建后台线程启动服务器�?好处是不会阻塞界面�?
wsock.tcp.simpleHttpServer.startUrl() 函数
实际上就是调�?wsock.tcp.simpleHttpServer.mainThread
这个函数在界面线程内启动线程并返回访问地址，自动分配空闲端口，自动创建服务器线程，
并在界面线程退出前自动退出服务器线程，最适合用于创建软件内嵌�?HTTP 服务端�?*/

//服务�?aardio 支持模板语法�?https://www.aardio.com/zh-cn/doc/language-reference/templating/syntax.html
var url = wsock.tcp.simpleHttpServer.startUrl("/.www/main.aardio");//参数支持 aardio 工程嵌入资源目录路径
//上面的函数可以重复调用，不会重复创建新的 HTTP 服务器端�?
import web.form;
var wb = web.form(winform);

//用浏览器组件打开网页试试
wb.go(url);

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Web/HTTPServer/simpleHttpServer.startUrl.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Web/HTTPServer/simpleHttpServer.startUrl.md')

