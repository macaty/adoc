[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# sys.upnp.nat 库模块帮助文�?
## sys.upnp 成员列表

通用即插即用 Universal Plug and Play

### sys.upnp.nat

Network Address Translation 自动端口映射

### sys.upnp.nat()

创建 UPnP 自动端口映射管理�?

如果设备不支持自动端口映射或连接到受限的访客网络则所有函数忽略不执行,

注意在XP系统上此对象的所有函数也会忽略不执行

[返回对象:sysUpnpNatObject](#sysUpnpNatObject)

## sysUpnpNatMappingPortObject 成员列表

### sysUpnpNatMappingPortObject.description

描述

### sysUpnpNatMappingPortObject.editDescription()

设置描述,参数应为字符�?
### sysUpnpNatMappingPortObject.editInternalClient()

设置内网IP地址或主机名,参数应为字符�?
### sysUpnpNatMappingPortObject.editInternalPort()

设置内网端口,参数应为数�?
### sysUpnpNatMappingPortObject.enable()

设置是否启用,即修�?enabled 属性的�?

参数可为 true �?false

### sysUpnpNatMappingPortObject.enabled

是否启用

注意这是只读属�?

修改此属性应当调�?enable 函数

### sysUpnpNatMappingPortObject.externalIPAddress

外网 IP 地址

### sysUpnpNatMappingPortObject.externalPort

外网端口

### sysUpnpNatMappingPortObject.internalClient

内网IP地址或主机名

### sysUpnpNatMappingPortObject.internalPort

内网端口

### sysUpnpNatMappingPortObject.protocol

网络协议

## sysUpnpNatObject 成员列表

### sysUpnpNatObject.add

添加端口映射,

成功返回端口映射对象,失败返回null,

如果指定外网端口已映射到其他主机,则添加该端口会失�?

如果添加之前已映射到本机的端口则会成�?
### sysUpnpNatObject.add()

[返回对象:sysUpnpNatMappingPortObject](#sysUpnpNatMappingPortObject)

### sysUpnpNatObject.add(externalPort,protocol,internalPort,internalClient,description)

添加端口映射,

除参�?@1 以外，所有参数都是可选参�?

全部参数如下�?
@externalPort 外网端口,数�?

@protocol 网络协议,默认�?TCP"

@internalPort 内网端口,默认与外端端口相�?数�?
@internalClient 内网地址,默认获取本机联网的网卡IP地址,字符串�?
@description 描述,默认为空字符�?
### sysUpnpNatObject.close()

关闭对象,一般可省略

### sysUpnpNatObject.count

返回端口映射对象总数

### sysUpnpNatObject.each()

```aardio aardio
for index,mappingPort in sysUpnpNatObject.each() {

}

[返回对象:sysUpnpNatMappingPortObject](#sysUpnpNatMappingPortObject)

```

### sysUpnpNatObject.getTable()

返回所有端口映射数据为一个数组，

每个数组成员为包含以下字段的普通表对象�?
protocol 协议,

description 描述,

externalPort 外部端口,

externalIPAddress 外网地址,

internalPort 内网端口,

internalClient 内网地址,

comObject 此映射对象的 COM 对象

### sysUpnpNatObject.item()

[返回对象:sysUpnpNatMappingPortObject](#sysUpnpNatMappingPortObject)

### sysUpnpNatObject.item(externalPort,protocol)

获取指定的端口映射对�?

@externalPort 用一个数值指定外网端�?

@protocol 用一个字符串指定网络协议,省略则为"TCP"

### sysUpnpNatObject.remove(externalPort,protocol)

移除指定的端口映射对�?成功返回 true,

@externalPort 用一个数值指定外网端�?

@protocol 用一个字符串指定网络协议,省略则为"TCP"

### sysUpnpNatObject.valid()

检测当前系统以及路由器是否支持 UPnP 自动端口映射,

注意连接到路由器设置受限的访客网络也可能不支�?UPnP

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/sys/upnp/nat.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/sys/upnp/nat.md')

