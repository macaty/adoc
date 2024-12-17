[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# wsock.udp.asynClient 库模块帮助文�?
## udpAsynClientObject 成员列表

### udpAsynClientObject.asyncSelect(event,userMsgId,hwnd)

检测到由event参数指明的网络事件后,

事件到达向hwnd指定句柄的窗口发送userMsgId消息,

第二次调用此函数可省略句柄以及消息ID

失败返回null,以及错误信息,

成功返回true,以及上次调用此函数指定的event参数

### udpAsynClientObject.bind

绑定 IP 端口�?
### udpAsynClientObject.bind(IP,端口)

绑定 IP 端口�?
如果不指�?IP 则默认获取内�?IP 作为参数�?
成功返回 true�?
失败返回 null,错误信息,错误代码�?
同一套接字重复绑定会返回 10022（\_WSAEINVAL�?错误�?
重新绑定应当重新创建套接字�?
这就好比一张车票只能上一次车�?
不能在已经上车以后再要求车站修改车票上的上车地�?
### udpAsynClientObject.close()

关闭 UDP 客户端�?
如果未显式调用此函数，在对象析构�?将会自动调用�?
已关闭的套接字不能再使用�?
就好比用过的车票不能重复用，什么地方都有规则和限制�?
### udpAsynClientObject.connect(IP或域�?端口�?

连接指定的目�?IP 以及端口号�?
省略参数则使用此对象上次使用的目标地址�?
### udpAsynClientObject.getLocalIp()

返回本机 IP，端�?
### udpAsynClientObject.getRemoteAddress()

最后最后发送或接收�?sockaddr\_in 结构�?
[返回对象:sockaddrInObject](#sockaddrInObject)

### udpAsynClientObject.getRemoteIp()

返回最后发送或接收�?IP ,端口

### udpAsynClientObject.getopt(\_SO)

获取选项

参数 @1 使用 _SO_ 前缀的常量指定选项,参数 @2 使用结构体指定�?
如果不指定参�?@2 ,则获取一�?2位整型数�?

可选用参数@3指定设置层次，默认为SOL\_SOCKET

成功返回读取的结构体

### udpAsynClientObject.joinGroup(广播组IP地址,网络接口IP)

加入广播�?
参数 @2 可省�?
### udpAsynClientObject.leaveGroup(广播组IP地址,网络接口IP)

退出广播组

参数 @2 可省�?
### udpAsynClientObject.onReceive

```aardio aardio
udpAsynClientObject.onReceive = function(err){
    var str = udpServer.recvfrom(1024);/*收到数据*/
}

```

### udpAsynClientObject.recv(最大接收长�?

调用 connect 以后可以使用此函数接收数据包�?
如果参数不指定长度，则使用bufferSize指定的长�?
成功返回字符�?

失败返回null,错误代码

### udpAsynClientObject.recvfrom(缓冲区长�?IP或域�?端口�?

接收并返回数据，IP 端口号为可选参�?
### udpAsynClientObject.reuseAddress(true)

是否允许端口重用

### udpAsynClientObject.send(数据,长度)

调用 connect 以后可以使用此函数接收数据包发送数据包

### udpAsynClientObject.sendto(发送数�?IP或域�?端口�?

发送数据，IP端口号为可选参�?

成功返回 true

### udpAsynClientObject.setBroadcast(true)

允许广播

### udpAsynClientObject.setMulticastInterface()

设置组播网卡 IP，不指定参数自动取网卡IP

### udpAsynClientObject.setMulticastLoopback(true)

是否启用多播回�?
### udpAsynClientObject.setMulticastTtl()

设置组播报文的数据包的TTL

### udpAsynClientObject.setTimeouts(发送超�?接收超时)

设置超时,以亳秒为单位( 1 秒为 1000 毫秒)

### udpAsynClientObject.setopt(\_SO)

设置选项

参数 @1 使用 _SO_ 前缀的常量指定选项,参数 @2 使用结构体、数值、布尔值都可以

可选用参数@3指定设置层次，默认为SOL\_SOCKET

成功返回true

## wsock.udp 成员列表

### wsock.udp.asynClient

UDP 异步客户�?
### wsock.udp.asynClient()

创建 UDP 异步客户端�?
[返回对象:udpAsynClientObject](#udpAsynClientObject)

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/wsock/udp/asynClient.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/wsock/udp/asynClient.md')

