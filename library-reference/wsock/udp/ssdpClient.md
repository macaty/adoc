[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# wsock.udp.ssdpClient 库模块帮助文�?
## wsock.udp 成员列表

### wsock.udp.ssdpClient()

SSDP - 局域网简单设备发现协议客户端

[返回对象:wsockUdpSsdpClientObject](#wsockUdpSsdpClientObject)

## wsockUdpSsdpClientObject 成员列表

### wsockUdpSsdpClientObject.discover(st,mx)

查询设备

st为要查询的设备类�?mx �?1 �?5 的表示等待秒数的数�?
所有参数都可以省略

### wsockUdpSsdpClientObject.onDeviceDiscovered(info)

```aardio aardio
wsockUdpSsdpClientObject.onDeviceDiscovered = function(info){
    /*info 为局域网设备应答的数据报�?/
}

```

### wsockUdpSsdpClientObject.socket

UDP套接字对�?
[返回对象:udpAsynClientObject](#udpAsynClientObject)

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/wsock/udp/ssdpClient.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/wsock/udp/ssdpClient.md')

