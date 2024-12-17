[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# sys.volume 库模块帮助文�?
## sys.volume 成员列表

存储卷相关函数�?
相关库：fsys.drives, sys.storage

### sys.volume.deviceDefine(文件路径)

将指定的目录映射为虚拟分�?
成功返回分区路径

### sys.volume.deviceDefine(文件路径,"Z:")

将指定的目录映射为虚拟分�?
成功返回分区路径

### sys.volume.deviceRemove("字符串参�?)

移除分区

### sys.volume.getAllDevice()

返回所有设备名

### sys.volume.getDeviceName(文件路径)

文件路径转换为设备名

### sys.volume.getDriveType(驱动器路�?

返回驱动器类�?
以\_DRIVE\_为前缀的常量表示不同类�?
### sys.volume.getFreeDrive()

获取未使用的盘符（自"C:"开始）

这个函数实际指向 fsys.drives.free 函数

### sys.volume.getInfo()

[返回对象:volumeinfoObject](#volumeinfoObject)

### sys.volume.getInfo(分区或完整路�?

返回分区信息,

参数可指定盘符或完整文件路径

盘符可带冒号也可以不�?
### sys.volume.getLogicalDrives()

返回一个包含所可用的逻辑分区盘符的数�?

盘符以冒号结�?
这个函数实际指向 fsys.drives.get

### sys.volume.getPathName(设备�?

设备名转换为文件路径

### sys.volume.getSpaceSize("C:\\")

获取分区空间大小, 剩余大小等信�?
参数可以是该驱动器下有效的目录路�?
### sys.volume.getSpaceSize()

[返回对象:valuespacesizeObject](#valuespacesizeObject)

### sys.volume.maxSpace(子目录路�?

将指定的子目录路径转换为空间最大的分区下的完整路径�?
返回转换后的路径

### sys.volume.setLabel("字符串参�?,"卷标")

设置区分卷标

## valuespacesizeObject 成员列表

### valuespacesizeObject.availablePercentage

有效空间百分�?
### valuespacesizeObject.avaliableSize

剩余有效空间大小

返回值为math.size64对象

[返回对象:mathSize64Object](../math/_.html#mathSize64Object)

### valuespacesizeObject.freePercentage

剩余空间百分�?
### valuespacesizeObject.freeSize

剩余空间大小

返回值为math.size64对象

[返回对象:mathSize64Object](../math/_.html#mathSize64Object)

### valuespacesizeObject.totalSize

总大�?
返回值为math.size64对象

[返回对象:mathSize64Object](../math/_.html#mathSize64Object)

## volumeinfoObject 成员列表

### volumeinfoObject.drive

分区路径

### volumeinfoObject.flag

标志�?
### volumeinfoObject.fsys

文件系统

### volumeinfoObject.label

卷名

### volumeinfoObject.maxlen

文件路径最大长�?
### volumeinfoObject.serial

序列�?
### volumeinfoObject.serialNum

序列�?数�?

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/sys/volume.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/sys/volume.md')

