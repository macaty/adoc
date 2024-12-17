[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# wsock.tcp.server 库模块帮助文�?
## wsock.tcp.server 成员列表

TCP服务�?
### wsock.tcp.server.closeById(serverId)

参数指定wsock.tcp.server对象的ID属�?
关闭指定ID的服务器

### wsock.tcp.server.getFreePort(ip,...)

获取空闲TCP服务端口�?
IP参数需要与实际创建服务器使用的IP参数完全一致，

可选在参数中使用数值数组或任意个数值参数指定优先测试的端口号，

如果没有找到参数指定的空闲凋�?则自动分配空闲端口，

动态分配空闲端口为49152�?5535之间的值，

XP系统则为 1025�?000之间的值，

命令行输�?netsh int ipv4 show dynamicport tcp 看动态端口范围，

安装 Hyper-V 会导致动态起始端口变�?1024 导致常用端口冲突

### wsock.tcp.server.isFreePort(port,ip)

检查参数指定的端口号是否空�?
如果不写IP，则默认设为"0.0.0.0"

## WsockTcpServerObject 成员列表

### WsockTcpServerObject.\_serverAddress

服务端监听地址

[返回对象:sockaddrInObject](#sockaddrInObject)

### WsockTcpServerObject.beforeClose()

```aardio aardio
WsockTcpServerObject.beforeClose = function(){
    /*服务器关闭前调用此函�?/
}

```

### WsockTcpServerObject.close()

关闭 TCP 服务�?
### WsockTcpServerObject.forever(回调函数)

```aardio aardio
WsockTcpServerObject.forever(
    function(acceptSocket){
        var request = wsock.tcp.client(,acceptSocket)
    }
)

```

### WsockTcpServerObject.getLocalIp()

返回当前绑定的IP,端口�?
### WsockTcpServerObject.id

服务器唯一ID,字符�?
### WsockTcpServerObject.listen(请求队列大小)

监听绑定�?IP 端口

## wsock.tcp 成员列表

### wsock.tcp.server()

[返回对象:WsockTcpServerObject](#WsockTcpServerObject)

### wsock.tcp.server(IP,端口,请求队列大小)

创建TCP服务�?所有参数可�?

如果不写IP，则默认设为"0.0.0.0"也即监听本机所有IP,访问此服务端也不限制IP

限制仅本机可以访问建议写127.0.0.1

端口�?或省略则自动查找1025以后的空闲端�?
注意0-1023为系统通用服务保留端口,

1024-49151为用户服务端�?其中大约%9已由IANA注册分配

49152-65535为私有或动态分配的临时端口

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/wsock/tcp/server.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/wsock/tcp/server.md')

