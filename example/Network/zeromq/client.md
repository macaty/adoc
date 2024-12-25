[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 客户�?
```aardio aardio
//客户�?import zeromq;
import console.int;

var context = zeromq.context(10)
//request模式socket与服务端的reply模式配对使用
var requester = context.zmq_socket_request() ;

requester.connect( "tcp://localhost:5559" )
if( requester.connect( "tcp://localhost:5559" ) ){
   console.log("连接成功")
}

var msg = zeromq.message("服务端你�?)
requester.sendMsg(msg)
msg.close();

var reply = zeromq.message()
requester.recvMsg(reply);
console.log ("客户端收到消�?", reply.getString() );
reply.close()

//关闭socket,不然context.term()无法退�?requester.close();

context.term();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Network/zeromq/client.md)

