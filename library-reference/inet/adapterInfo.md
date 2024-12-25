[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# inet.adapterInfo 库模块帮助文�?
参考文�?
inet.adapterInfo.each(family,flags) 返回的为 IP\_ADAPTER\_ADDRESSES 结构体�?
关于 family,flags 参数的用法与 IP\_ADAPTER\_ADDRESSES 结构体的详细说明请参考：
[https://learn.microsoft.com/en-us/windows/win32/api/iptypes/ns-iptypes-ip\_adapter\_addresses\_lh](https://learn.microsoft.com/en-us/windows/win32/api/iptypes/ns-iptypes-ip_adapter_addresses_lh)

结构体字段首字母�?aardio 中需要改为小写�?
## inet.adapterInfo 成员列表

用于获取网络适配器与配置信息（不含禁用的网卡）�?
�?inet.adapter 获取到的信息更多一些�?
sys.networkCards 则用于获取网卡硬件信息（含禁用网卡）�?
可使�?com.wmi 查询 Win32\_NetworkAdapter 得到网卡信息,

com.wmi 查询 Win32\_NetworkAdapterConfiguration 得到网络适配器连接配�?
### inet.adapterInfo.each()

[返回对象:netAdapterAddressObject](#netAdapterAddressObject)

### inet.adapterInfo.each(family,flags)

```aardio aardio
//遍历所有连�?for adapterInfo in inet.adapterInfo.each() {
    /*adapterInfo 为包含网络适配器与 IP 配置信息的结构体*/
}

```

### inet.adapterInfo.get

查找并返回网络适配器与配置信息

### inet.adapterInfo.get()

[返回对象:netAdapterAddressObject](#netAdapterAddressObject)

### inet.adapterInfo.get(adapterName)

查找并返回网络适配器与配置信息�?
@adapterName 用字符串指定 GUID 格式适配�?
## netAdapterAddressObject 成员列表

### netAdapterAddressObject.adapterName

适配器名称， GUID 格式�?
�?netConnectionId 字段可以获取显示名称

adapterName 是永久性的，用户无法修改�?
netConnectionId 则可以改�?
### netAdapterAddressObject.address

MAC地址,数值格�?
### netAdapterAddressObject.description

连接描述

### netAdapterAddressObject.dnsSuffix

DNS 后缀�?
### netAdapterAddressObject.eachAnycastAddress()

```aardio aardio
for addr,strAddr in netAdapterAddressObject.eachAnycastAddress(){
    /*遍历任播地址，strAddr 为字符串格式 IP 地址�?addr 为当�?IP_ADAPTER_ADDRESS 结构体，不用管�?/
}

```

### netAdapterAddressObject.eachDnsServerAddress()

```aardio aardio
for addr,strAddr in netAdapterAddressObject.eachDnsServerAddress(){
    /*遍历 DNS 服务器地址，strAddr 为字符串格式 IP 地址�?addr 为当�?IP_ADAPTER_ADDRESS 结构体，不用管�?/
}

```

### netAdapterAddressObject.eachMulticastAddress()

```aardio aardio
for addr,strAddr in netAdapterAddressObject.eachMulticastAddress(){
    /*遍历多播地址，strAddr 为字符串格式 IP 地址�?addr 为当�?IP_ADAPTER_ADDRESS 结构体，不用管�?/
}

```

### netAdapterAddressObject.eachUnicastAddress()

```aardio aardio
for addr,strAddr in netAdapterAddressObject.eachUnicastAddress(){
    /*遍历单播地址，strAddr 为字符串格式 IP 地址�?addr 为当�?IP_ADAPTER_ADDRESS 结构体，不用管�?/
}

```

### netAdapterAddressObject.flags

数值表示的设置选项

### netAdapterAddressObject.ifIndex

网卡索引

### netAdapterAddressObject.ifType

适配器类�?
### netAdapterAddressObject.ifTypeLoopback

适配器类型为软件实现的回环网�?
### netAdapterAddressObject.ifTypeWireless

适配器类型为无线网卡

### netAdapterAddressObject.ipv6IfIndex

IPv6 网卡索引

### netAdapterAddressObject.mac

MAC地址,文本格式

### netAdapterAddressObject.mtu

最大传输单元大�?
### netAdapterAddressObject.netConnectionId

连接友好名称�?
也就是控制面板里显示的网络连接名

### netAdapterAddressObject.operStatus

由多个表示不同网卡操作状态的数值按位或得到的�?�?
### netAdapterAddressObject.operStatusUp

网卡为可用的活动状�?
[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/inet/adapterInfo.md)

