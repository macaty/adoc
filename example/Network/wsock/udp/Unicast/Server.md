[aardio 文档](../../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 服务�?
```aardio aardio
import console.int;
import wsock.udp.client;

console.log("UDP服务端已启动")
var udpServer = wsock.udp.client();

//绑定 IP 端口，注意同一套接字不能重复绑�?var ok,err,errCode = udpServer.bind( "0.0.0.0",50 );
if( !ok ){
    udpServer.close();

    console.log("未监听成�?,err,errCode);
    return;
}

//接收数据
var str = udpServer.recvfrom(1024)
console.log("服务器收�?",str)
thread.delay(1000)

//发送数�?udpServer.sendto("ok1");
thread.delay(1000)

//发送数�?udpServer.sendto("ok2");
udpServer.close();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Network/wsock/udp/Unicast/Server.md)

