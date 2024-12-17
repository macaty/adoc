[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# sys.storage 库模块帮助文�?
## sys.storage 成员列表

存储设备属�?
不需要管理权限�?
相关库：fsys.drives, sys.volume

### sys.storage.getDeviceNumber("设备�?)

参数指定分区设备�?或直接指定盘�?
返回存储设备序号

### sys.storage.getDeviceNumber()

[返回对象:sysStorageDeviceNumberObject](#sysStorageDeviceNumberObject)

### sys.storage.getDevices

返回硬盘分区

### sys.storage.getDevices(flat,isUsb)

返回硬盘分区,所有参数都可省略�?
如果 @flat 参数�?true 则返回分区盘符数�?

否则返回硬盘分区列表,键为设备序号,值为该设备创建的分区盘符数组�?
注意设备序号不一定是连续的数值�?
@isUsb 如果�?true，则仅返�?USB 设备创建的分�?
### sys.storage.getUsbDevices

返回 U�?分区

### sys.storage.getUsbDevices()

返回U盘分区列表，

键为 U�?设备序号,值为�?U�?建立的所有分区盘符数组�?
注意设备序号不一定是连续的数值�?
### sys.storage.getUsbDevices(true)

返回 U�?分区盘符数组

### sys.storage.isUsbDevice("设备路径)

检测是�?U�?

参数可指定设备名、分区盘符、存储设备序号等

### sys.storage.queryProperty("设备路径)

可指定设备名、分区盘符、存储设备序号等

如果不指定参数则自动获取硬盘设备路径

### sys.storage.queryProperty()

[返回对象:sysStoragePropertyObject](#sysStoragePropertyObject)

## sysStorageDeviceNumberObject 成员列表

### sysStorageDeviceNumberObject.deviceNumber

设备序号

### sysStorageDeviceNumberObject.deviceType

类型

使用 _FILE\_DEVICE_ 前缀常量

### sysStorageDeviceNumberObject.partitionNumber

分区序号

## sysStoragePropertyObject 成员列表

### sysStoragePropertyObject.busType

总线类型

使用 \_BusType 前缀常量

例如U盘是 \_BusTypeUsb,其值为7

### sysStoragePropertyObject.commandQueueing

是否支持命令队列

### sysStoragePropertyObject.deviceType

设备类型

### sysStoragePropertyObject.deviceTypeModifier

SCSI-2额外的设备类�?
### sysStoragePropertyObject.isUsbDevice

是否 USB 设备

### sysStoragePropertyObject.productId

产品ID

### sysStoragePropertyObject.productRevision

产品版本

### sysStoragePropertyObject.removableMedia

是否可移�?
### sysStoragePropertyObject.serialNumber

序列�?
### sysStoragePropertyObject.vendorId

厂商ID

### 自动完成常量

\_BusType1394=4

\_BusTypeAta=3

\_BusTypeAtapi=2

\_BusTypeFibre=6

\_BusTypeMaxReserved=0x7F

\_BusTypeRAID=8

\_BusTypeScsi=1

\_BusTypeSsa=5

\_BusTypeUnknown=0

\_BusTypeUsb=7

\_PropertyExistsQuery=1

\_PropertyMaskQuery=2

\_PropertyQueryMaxDefined=3

\_PropertyStandardQuery=0

\_StorageAdapterProperty=1

\_StorageDeviceProperty=0

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/sys/storage.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/sys/storage.md')

