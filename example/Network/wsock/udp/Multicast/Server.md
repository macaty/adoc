[aardio 鏂囨。](../../../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鏈嶅姟绔?
```aardio aardio
import console;
import wsock.udp.client;

console.log("UDP鏈嶅姟绔凡鍚姩")

var udpServer = wsock.udp.client();

//璋冪敤bind()灏嗚濂楁帴鍙ｅ拰 鏈湴缃戠粶鍦板潃鑱旂郴鍦ㄤ竴璧?if( !udpServer.bind( "0.0.0.0",501 ) ){
    udpServer.close();
    console.log("鏈洃鍚垚鍔?);
    console.pause();
    return false;
}

udpServer.joinGroup("239.215.251.230")
var str = udpServer.recvfrom(1024)
console.log("鏈嶅姟鍣ㄦ敹鍒?",str)

sleep(1000)
udpServer.sendto("ok1");

sleep(1000)
udpServer.sendto("ok2");

udpServer.close();
console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Network/wsock/udp/Multicast/Server.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 服务器报告访问的文件是隐藏的。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Network/wsock/udp/Multicast/Server.md')

