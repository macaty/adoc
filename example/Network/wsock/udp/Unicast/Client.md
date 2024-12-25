[aardio 文档](../../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 客户�?
```aardio aardio
import console;
import wsock.udp.client;

//创建客户�?var udpClient = wsock.udp.client();

//发送数�?console.log( udpClient.sendto("test","127.0.0.1",50) );
console.log("对方端口", udpClient.getRemoteIp() )

//接收数据
var str = udpClient.recvfrom( )
console.log("收到服务器的反馈",str)
console.log("对方端口", udpClient.getRemoteIp() )

//得到对方端口以后也可�?connect
udpClient.connect();

//接收数据
var str= udpClient.recvfrom( )
console.log("收到服务器的反馈2",str)

console.log("发送完�?)
console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Network/wsock/udp/Unicast/Client.md)

