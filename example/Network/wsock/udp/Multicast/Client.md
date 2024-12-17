[aardio 鏂囨。](../../../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 瀹㈡埛绔?
```aardio aardio
import console;
import wsock.udp.client;

var udpClient = wsock.udp.client();
console.log( udpClient.sendto("test","239.215.251.230",501) );
console.log("瀵规柟绔彛", udpClient.getRemoteIp() )

var str = udpClient.recvfrom( )
console.log("鏀跺埌鏈嶅姟鍣ㄧ殑鍙嶉",str)
console.log("瀵规柟绔彛", udpClient.getRemoteIp() )

//寰楀埌瀵规柟绔彛浠ュ悗涔熷彲浠onnect
udpClient.connect();
var str= udpClient.recvfrom( )
console.log("鏀跺埌鏈嶅姟鍣ㄧ殑鍙嶉2",str)

console.log("鍙戦�佸畬姣?)
console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Network/wsock/udp/Multicast/Client.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 服务器报告访问的文件是隐藏的。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Network/wsock/udp/Multicast/Client.md')

