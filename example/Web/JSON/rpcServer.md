[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: HTTP-JSON-RPC 服务�?
```aardio aardio
//HTTP-JSON-RPC 服务�?
import win.ui;
/*DSG{{*/
mainForm = win.form(text="aardio form";right=759;bottom=469)
mainForm.add(
edit={cls="edit";left=18;top=22;right=728;bottom=404;edge=1;multiline=1;z=1}
)
/*}}*/

import wsock.tcp.simpleHttpServer;
namespace wsock.tcp.simpleHttpServer{
    //startIp = "0.0.0.0"; //不限制本�?IP
    startPort = 8610; //不指定端口时会自动分配空闲端�?    threadGlobal = { mainForm = ..mainForm }; //指定 HTTP 服务线程的默认全局变量,注意定义线程函数的作用域同名变量不能是局部变�?}

mainForm.edit.print("http://127.0.0.1:8610/jsonrpc 已启�?);

//io.open() //打开控制台查看线程错误信�?var url = wsock.tcp.simpleHttpServer.startUrl(
    function(response,request){
        if( request.path !="/jsonrpc" ) response.error(404);
        mainForm.edit.print(request.postData());

        import web.rpc.jsonServer;
        var jsonServer = web.rpc.jsonServer();

        //可以定义允许客户端调用的函数
        jsonServer.hello = function(name){
            mainForm.edit.print("hello 函数被调用了,参数�?,name);

            /*
            第一个返回值为客户端返回�?result)�?            第二个返回值为错误对象(error)
            */
            if(!name) return null,-32602/*_JSONRPC_INVALID_PARAMS*/;
            return "hello " + name;
        }

        //也可以指定允许客户端调用的其他对�?        jsonServer.aardio = {

            /*
            如果函数名第一个字符为$，则第一个回调参数为$�?            $参数表示可以在jsonServer.rpc.run函数的参数中指定,如果不指定则默认为当�?request对象
            */
            $hello = function($,name){
                return "aardio.hello " + name;
            }

            err = function(){
                error("假装抛出异常试试",2)
            }
        }

        /*
            //下面这种写法也可�?            jsonServer.rpc.external = {
                hello = function(name){

                }
            }
        */

        jsonServer.rpc.onError = function(err,requestData){
            //未捕获的服务端异常会触发这个函数，客户端错误代码�?_JSONRPC_INTERNAL_ERROR
            mainForm.edit.print("发生错误",err,requestData)
        }

        //运行服务�?可选在参数中指定回�?参数
        jsonServer.rpc.run();
    }
);

mainForm.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Web/JSON/rpcServer.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Web/JSON/rpcServer.md')

