[aardio 鏂囨。](../../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: UDP 骞挎挱鏈嶅姟绔?
```aardio aardio
//UDP 骞挎挱
import win.ui;
/*DSG{{*/
var winform = win.form(text="UDP 骞挎挱鏈嶅姟绔?;right=759;bottom=469)
winform.add(
btnClient={cls="button";text="娴嬭瘯瀹㈡埛绔?;left=535;top=390;right=723;bottom=455;z=2};
edit={cls="edit";left=22;top=17;right=732;bottom=353;edge=1;multiline=1;z=1}
)
/*}}*/

import wsock.udp.asynClient;
var udpServer = wsock.udp.asynClient();

//鍏佽骞挎挱
udpServer.setBroadcast(true);

//鍚屼竴濂楁帴瀛椾笉鑳介噸澶嶇粦瀹氥�?udpServer.bind("0.0.0.0",1000);

//鏀跺埌鏁版嵁瑙﹀彂锛宔rr 涓洪敊璇俊鎭紙鏃犻敊璇负 null锛?udpServer.onReceive = function(err){
    var str = udpServer.recvfrom(1024);
    winform.edit.print(str)
}

winform.btnClient.oncommand = function(id,event){

    //鍒涘缓瀹㈡埛绔鎺ュ瓧
    var udpClient = wsock.udp.client();

    //鍏佽骞挎挱
    udpClient.setBroadcast(true);

    //鍙戦�佹暟鎹?    udpClient.sendto("test","255.255.255.255",1000);
}

winform.show()
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Network/wsock/udp/broadcast.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Network/wsock/udp/broadcast.md')

