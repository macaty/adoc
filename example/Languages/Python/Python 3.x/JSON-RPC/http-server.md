[aardio 文档](../../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 Python 创建 JSON RPC 服务�?
```aardio aardio
//aardio 调用 Python 创建 JSON RPC 服务�?import win.ui;
/*DSG{{*/
var winform = win.form(text="JSON-RPC";right=759;bottom=469)
winform.add(
edit={cls="edit";left=13;top=18;right=734;bottom=444;edge=1;multiline=1;z=1}
)
/*}}*/

import wsock;
winform.freePort = wsock.getFreePort();

/*
启动 JSON-RPC 服务端线�? Python )
一个线程跑 Python，别的线程就不要�?Python�?Pyhton 多线程操作不慎会崩溃，而且也不能算是真的多线程，所以请避开这个坑�?*/
thread.invoke(
    function(winform){
        import py3;
        import py3.lib.jsonrpclib;

        //设置 Python 全局变量
        py3.main.freePort = py3.int(winform.freePort);

        var pyCode = /**
from jsonrpclib.SimpleJSONRPCServer import SimpleJSONRPCServer

# 指定 logRequests=False 就不用打开控制台，不然没有控制台会直接退�?server = SimpleJSONRPCServer(('localhost', freePort),logRequests=False)
server.register_function(pow)
server.register_function(lambda x,y: x+y, 'add')
server.register_function(lambda x: x, 'ping')
server.serve_forever()
        **/

        py3.exec(pyCode);

    },winform
)

//启动 JSON-RPC 客户端线�? aardio )
thread.invoke(
    function(winform){
        thread.delay(1000);

        import web.rpc.jsonClient;

        //创建JSON-RPC 2.0客户�?        var client = web.rpc.jsonClient("http://127.0.0.1:" + winform.freePort)

        //调用远程对象和函�?aardio.$hello
        var rep = client.add(12,3);

        winform.edit.print( "返回值：", rep.result );

        winform.edit.print( client.rpc.lastResponse() );
    },winform
)

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python 3.x/JSON-RPC/http-server.md)

