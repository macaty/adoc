[aardio 文档](../../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 客户�?
```aardio aardio
//客户�?import console;

import wsock.tcp.client;
var socket = wsock.tcp.client()

socket.connect("127.0.0.1",7510)
console.log("连接端口成功,正在接收文件!")

var buffer = raw.buffer(0x1000);
var file = io.file("/test.zip","w+b");//注意 io.file 默认是文本方式写入的,b指定二进制模�?var size = math.size64();
for(readSize,remainSize in socket.eachReadBuffer(buffer) ){
    io.stdout.write('\r' +  size.add(readSize).format() )
    file.writeBuffer(buffer,readSize);
}
file.close();

console.log('\n' + "客户端接收文件完�?);
socket.close();

console.pause()

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Network/wsock/tcp/FileTransfer/Client.md)

