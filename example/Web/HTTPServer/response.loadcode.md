[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 下载文件

```aardio aardio
//下载文件
import console;
import wsock.tcp.simpleHttpServer;

//创建 HTTP 服务端，不指定端口时自动分配空闲端口
var server = wsock.tcp.simpleHttpServer("127.0.0.1",/*8081*/);

//指定网站根目录，不允许下载根目录之外的文�?server.documentRoot = "~/example/Graphics/";

//显示服务器地址
console.log( server.getUrl() )

//在浏览器打开服务器地址
raw.execute( server.getUrl() );

//运行 HTTP 服务端处理程�?server.run(
    function(response,request,session){

        //处理请求，request.path 是客户端请求的文件路径�?        if( request.path = "/test.jpg" ){

            /*
            如果参数�?*.aardio 则执行服务端代码。否则下载文件�?            这个函数已经处理好所有事件，一般没必要自己重新去写�?HTTP 下载功能（工作量和难度都不小）�?            */
            response.loadcode("/.gdip.jpg");
            /*
            如果需要更多功能，例如重启，更换根目录等等�?            请查看『扫码传文件』范例�?            */
        }
        else{
            //自动支持服务端模板语�?https://www.aardio.com/zh-cn/doc/language-reference/templating/syntax.html
            loadcodex(`
        <!doctype html>
        <html><head></head><body style="white-space:pre">
        <a href="/test.jpg">/test.jpg</a> </body>
        </html>`);
        }
    }
)

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Web/HTTPServer/response.loadcode.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Web/HTTPServer/response.loadcode.md')

