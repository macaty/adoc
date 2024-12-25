[aardio 文档](../../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 客户�?
```aardio aardio
import console;
import wsock.udp.client;

var udpClient = wsock.udp.client();
console.log( udpClient.sendto("test","239.215.251.230",501) );
console.log("对方端口", udpClient.getRemoteIp() )

var str = udpClient.recvfrom( )
console.log("收到服务器的反馈",str)
console.log("对方端口", udpClient.getRemoteIp() )

//得到对方端口以后也可以connect
udpClient.connect();
var str= udpClient.recvfrom( )
console.log("收到服务器的反馈2",str)

console.log("发送完�?)
console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Network/wsock/udp/Multicast/Client.md)

