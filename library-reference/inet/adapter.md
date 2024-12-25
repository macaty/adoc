[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# inet.adapter 库模块帮助文�?
## inet.adapter 成员列表

用于获取网络适配器信息（不含禁用的网卡与回环网卡�?
inet.adapterAddresses 可以得到更多信息�?
sys.networkCards 取网卡硬件信息（含禁用的网卡）�?
可使�?com.wmi 查询 Win32\_NetworkAdapter 得到网卡信息,

com.wmi 查询 Win32\_NetworkAdapterConfiguration 得到网络适配器连接配�?
### inet.adapter.each()

```aardio aardio
//遍历所有连�?for adptInfo in inet.adapter.each() {
    /*adptInfo 为网络连接信�?/
}

[返回对象:netAdptInfoObject](#netAdptInfoObject)

```

### inet.adapter.get

查找并返回网络适配器与配置信息

### inet.adapter.get()

[返回对象:netAdptInfoObject](#netAdptInfoObject)

### inet.adapter.get(adapterName)

查找并返回网络适配器与配置信息�?
@adapterName 用字符串指定 GUID 格式适配�?
## ipaddrStringObject 成员列表

### ipaddrStringObject.context

```aardio aardio
_MIB_IF_TYPE_OTHER=@1/*_MIB_IF_TYPE_OTHER*/

```

### ipaddrStringObject.eachAddress()

遍历IP列表

[返回对象:ipaddrStringObject](#ipaddrStringObject)

### ipaddrStringObject.getNextIpAddrString()

获取下一个IP地址

[返回对象:ipaddrStringObject](#ipaddrStringObject)

### ipaddrStringObject.ipAddress

IP地址

### ipaddrStringObject.ipMask

掩码

## netAdptInfoObject 成员列表

### netAdptInfoObject.adapterName

网卡名称

### netAdptInfoObject.address

MAC地址,数值格�?
### netAdptInfoObject.addressLength

网卡地址长度

### netAdptInfoObject.description

网卡描述

### netAdptInfoObject.dhcpEnabled

是否启用DHCP

### netAdptInfoObject.dhcpServer

[返回对象:ipaddrStringObject](#ipaddrStringObject)

### netAdptInfoObject.eachAddress()

```aardio aardio
for addr,strAddr in netAdptInfoObject.eachAddress(){
    /*遍历 IP 地址，strAddr 为字符串格式 IP 地址�?addr 为当�?IP_ADAPTER_INFO 结构体，不用管�?/
}

```

### netAdptInfoObject.eachDhcpServer()

```aardio aardio
for addr,strAddr in netAdptInfoObject.eachDhcpServer(){
    /*遍历 DHCP 服务器地址，strAddr 为字符串格式 IP 地址�?addr 为当�?IP_ADAPTER_INFO 结构体，不用管�?/
}

```

### netAdptInfoObject.eachGateway()

```aardio aardio
for addr,strAddr in netAdptInfoObject.eachGateway(){
    /*遍历网关地址，strAddr 为字符串格式 IP 地址�?addr 为当�?IP_ADAPTER_INFO 结构体，不用管�?/
}

```

### netAdptInfoObject.gatewayList

[返回对象:ipaddrStringObject](#ipaddrStringObject)

### netAdptInfoObject.haveWins

是否启动了Wins服务

### netAdptInfoObject.index

网络接口索引�?
### netAdptInfoObject.ipAddressList

[返回对象:ipaddrStringObject](#ipaddrStringObject)

### netAdptInfoObject.leaseExpires

DHCP租赁失效时间

### netAdptInfoObject.leaseObtained

DHCP租赁时间

### netAdptInfoObject.mac

MAC地址,文本格式

### netAdptInfoObject.netConnectionId

网络连接�?
### netAdptInfoObject.pnpInstanceId

设备实例 ID，由"设备ID\\实例ID"组成,

设备实例 ID用于 process.devcon 作为参数时前面要添加@

### netAdptInfoObject.primaryWinsServer

[返回对象:ipaddrStringObject](#ipaddrStringObject)

### netAdptInfoObject.secondaryWinsServer

[返回对象:ipaddrStringObject](#ipaddrStringObject)

### netAdptInfoObject.type

网络接口类型

例如 \_MIB\_IF\_TYPE\_ETHERNET

### 自动完成常量

\_IF\_TYPE\_IEEE80211=71

\_MIB\_IF\_TYPE\_ETHERNET=6

\_MIB\_IF\_TYPE\_FDDI=0xF

\_MIB\_IF\_TYPE\_LOOPBACK=0x18

\_MIB\_IF\_TYPE\_PPP=0x17

\_MIB\_IF\_TYPE\_SLIP=0x1C

\_MIB\_IF\_TYPE\_TOKENRING=9

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/inet/adapter.md)

