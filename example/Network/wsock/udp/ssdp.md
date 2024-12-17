[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: SSDP客户�?- 发现局域网设备

```aardio aardio
//SSDP 发现设备
//请参�?golang.mdns 扩展库范�?import win.ui;
/*DSG{{*/
var winform = win.form(text="SSDP客户�?- 发现局域网设备";right=1044;bottom=715)
winform.add(
btnDiscover={cls="button";text="发现局域网设备";left=789;top=645;right=979;bottom=698;db=1;dr=1;z=2};
edit={cls="edit";left=15;top=23;right=1021;bottom=625;db=1;dl=1;dr=1;dt=1;edge=1;multiline=1;vscroll=1;z=1}
)
/*}}*/

import web.json;
import wsock.udp.ssdpClient;
var ssdpClient = wsock.udp.ssdpClient();

//异步响应局域网设备应答的数据报�?ssdpClient.onDeviceDiscovered = function(result){
    winform.edit.print(result)
}

//发起 SSDP 查询
winform.btnDiscover.oncommand = function(id,event){
    ssdpClient.discover();
}

winform.show()
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Network/wsock/udp/ssdp.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Network/wsock/udp/ssdp.md')

