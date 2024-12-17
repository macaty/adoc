[aardio 鏂囨。](../../../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 瀹㈡埛绔?
```aardio aardio
//瀹㈡埛绔?import console;

import wsock.tcp.client;
var socket = wsock.tcp.client()

socket.connect("127.0.0.1",7510)
console.log("杩炴帴绔彛鎴愬姛,姝ｅ湪鎺ユ敹鏂囦欢!")

var buffer = raw.buffer(0x1000);
var file = io.file("/test.zip","w+b");//娉ㄦ剰 io.file 榛樿鏄枃鏈柟寮忓啓鍏ョ殑,b鎸囧畾浜岃繘鍒舵ā寮?var size = math.size64();
for(readSize,remainSize in socket.eachReadBuffer(buffer) ){
    io.stdout.write('\r' +  size.add(readSize).format() )
    file.writeBuffer(buffer,readSize);
}
file.close();

console.log('\n' + "瀹㈡埛绔帴鏀舵枃浠跺畬鎴?);
socket.close();

console.pause()

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Network/wsock/tcp/FileTransfer/Client.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 服务器报告访问的文件是隐藏的。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Network/wsock/tcp/FileTransfer/Client.md')

