[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# sys.networkCards 库模块帮助文�?
## sys.networkCards 成员列表

用于获取网卡硬件信息（含禁用网卡）�?
�?inet.adapter，inet.adapterInfo 可获取网络适配器配置信息�?
可使�?com.wmi 查询 Win32\_NetworkAdapter 得到网卡信息,

com.wmi 查询 Win32\_NetworkAdapterConfiguration 得到网络适配器连接配�?
### sys.networkCards.each()

[返回对象:SysNetworkCardObject](#SysNetworkCardObject)

### sys.networkCards.each(enumerators...)

```aardio aardio
for networkCard in sys.networkCards.each(){
    /*networkCard 是包含网卡信息的表对�?@enumerators 参数可用一个字符串数组，或任意个字符串参数指定枚举类型�?例如 "PCI","USB", 一般不必指�?/
}

```

## SysNetworkCardObject 成员列表

### SysNetworkCardObject.adapterName

适配�?GUID

### SysNetworkCardObject.description

硬件描述

### SysNetworkCardObject.hardwareId

设备 ID

### SysNetworkCardObject.netConnectionId

网络连接名称

### SysNetworkCardObject.pnpInstanceId

设备实例 ID, �?设备 ID\\实例 ID"组成

用于 process.devcon 的参数时前面要加 "@" 字符

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/sys/networkCards.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/sys/networkCards.md')

