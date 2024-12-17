[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 设置多线程服务端

```aardio aardio
//设置多线程服务端
import win.ui;
/*DSG{{*/
mainForm = win.form(text="多线程服务端进阶";right=759;bottom=469)
mainForm.add(
edit={cls="edit";left=20;top=9;right=744;bottom=196;dl=1;dr=1;dt=1;edge=1;multiline=1;vscroll=1;z=1};
static={cls="static";text="Static";left=20;top=207;right=740;bottom=451;db=1;dl=1;dr=1;dt=1;z=2}
)
/*}}*/

import wsock.tcp.simpleHttpServer;

/*
可在 wsock.tcp.simpleHttpServer 名字空间指定 startUrl 函数的预设选项,
具体有哪些选项请查�?wsock.tcp.simpleHttpServer.startUrl() 函数源码�?直接使用 wsock.tcp.simpleHttpServer.mainThread 也行�?*/
namespace wsock.tcp.simpleHttpServer{
    //startIp = "0.0.0.0"; //不限制本�?IP
    //startPort = 8615; //不指定端口时会自动分配空闲端�?    threadGlobal = { mainForm = ..mainForm }; //指定 HTTP 服务线程的默认全局变量,注意定义线程函数的作用域同名变量不能是局部变�?}

//io.open() //打开控制台查看线程错误信�?var url = wsock.tcp.simpleHttpServer.startUrl(
    function(response,request,session){

        response.write("hello <a href='/test/" + string.random(10) + "'>点这�?/a>");
        mainForm.edit.print( "HTTP 请求�?,request.path );

        /*
        如果想更高级一点，这里还可以来�?web.rpc.jsonServer,
        参考「范�?/ Web 应用 / JSON / HTTP-RPC-JSON 服务�?�?        */
    }
);

import web.form;
var wb = web.form(mainForm.static);
wb.go(url);

mainForm.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Web/HTTPServer/simpleHttpServer.startUrl.app.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Web/HTTPServer/simpleHttpServer.startUrl.app.md')

