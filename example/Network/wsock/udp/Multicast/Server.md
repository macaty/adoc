[aardio 文档](../../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 服务�?
```aardio aardio
import console;
import wsock.udp.client;

console.log("UDP服务端已启动")

var udpServer = wsock.udp.client();

//调用bind()将该套接口和 本地网络地址联系在一�?if( !udpServer.bind( "0.0.0.0",501 ) ){
    udpServer.close();
    console.log("未监听成�?);
    console.pause();
    return false;
}

udpServer.joinGroup("239.215.251.230")
var str = udpServer.recvfrom(1024)
console.log("服务器收�?",str)

sleep(1000)
udpServer.sendto("ok1");

sleep(1000)
udpServer.sendto("ok2");

udpServer.close();
console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Network/wsock/udp/Multicast/Server.md)

