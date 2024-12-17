[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: JSON-RPC( HTTP )

```aardio aardio
//JSON-RPC( HTTP )
import win.ui;
/*DSG{{*/
var winform = win.form(text="JSON-RPC";right=759;bottom=469)
winform.add(
edit={cls="edit";left=13;top=18;right=734;bottom=444;edge=1;multiline=1;z=1}
)
/*}}*/

//开发环境安装模�?if(_STUDIO_INVOKED){
    import process.python.pip;
    process.python.pip.require("jsonrpclib")
}

//获取空闲端口
import wsock;
winform.rpcServerPort = wsock.getFreePort();

import process.python;
process.python.exec(`
from jsonrpclib.SimpleJSONRPCServer import SimpleJSONRPCServer

# 指定 logRequests=False 就不用打开控制台，不然没有控制台会直接退�?server = SimpleJSONRPCServer(('localhost', `+winform.rpcServerPort+`),logRequests=False)
server.register_function(pow)
server.register_function(lambda x,y: x+y, 'add')
server.register_function(lambda x: x, 'ping')
server.serve_forever()
`);

//启动 JSON-RPC 客户端线�? aardio )
thread.invoke(
    function(winform){
        thread.delay(1000);

        import web.rpc.jsonClient;

        //创建JSON-RPC 2.0客户�?        var client = web.rpc.jsonClient("http://127.0.0.1:" + winform.rpcServerPort)

        //调用远程对象和函�?aardio.$hello
        var rep = client.add(12,3);

        winform.edit.print( "返回值：", rep[["result"]] );

        winform.edit.print( client.rpc.lastResponse() );
    },winform
)

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python AnyVersion/jsonrpc-http.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python AnyVersion/jsonrpc-http.md')

