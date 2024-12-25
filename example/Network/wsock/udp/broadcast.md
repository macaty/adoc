[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: UDP 广播服务�?
```aardio aardio
//UDP 广播
import win.ui;
/*DSG{{*/
var winform = win.form(text="UDP 广播服务�?;right=759;bottom=469)
winform.add(
btnClient={cls="button";text="测试客户�?;left=535;top=390;right=723;bottom=455;z=2};
edit={cls="edit";left=22;top=17;right=732;bottom=353;edge=1;multiline=1;z=1}
)
/*}}*/

import wsock.udp.asynClient;
var udpServer = wsock.udp.asynClient();

//允许广播
udpServer.setBroadcast(true);

//同一套接字不能重复绑定�?udpServer.bind("0.0.0.0",1000);

//收到数据触发，err 为错误信息（无错误为 null�?udpServer.onReceive = function(err){
    var str = udpServer.recvfrom(1024);
    winform.edit.print(str)
}

winform.btnClient.oncommand = function(id,event){

    //创建客户端套接字
    var udpClient = wsock.udp.client();

    //允许广播
    udpClient.setBroadcast(true);

    //发送数�?    udpClient.sendto("test","255.255.255.255",1000);
}

winform.show()
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Network/wsock/udp/broadcast.md)

