[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 服务�?
```aardio aardio
//服务�?import zeromq;
import console.int;

var context = zeromq.context(1)

//replay模式socket与客户端的request模式配对使用
var responder = context.zmq_socket_reply()

if( ! responder.bind(  "tcp://*:5559") ){
    console.log( zeromq.lasterr() );
    return;
}
console.log("服务端已启动")

while (1) {

    var msg = zeromq.message();
    if( ! responder.recvMsg(msg) ){
        console.log( zeromq.lasterr() )
    }

    console.log("服务端收到消�?,msg.getString() );
    msg.close();

    //在这里可以添加其他代�?    sleep (1);

    // 发送消�?    msgReply = zeromq.message("客户端你�?);
    responder.sendMsg(msgReply);
    msgReply.close();

    //上面的代码也可以简化为一�?如下:
    //responder.send("客户端你�?)
    console.log("响应完毕")

}

//上面的代码会一直循环不会中�?
//如果使用break语句中断,则执行下面的代码释放资源
responder.close();
context.term();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Network/zeromq/server.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Network/zeromq/server.md')

