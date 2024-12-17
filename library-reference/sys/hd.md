[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# sys.hd 库模块帮助文�?
## sys.hd 成员列表

用于获取硬盘序列�?
注意在VISTA以后系统需要管理权�?
### sys.hd.getInfo()

读取硬盘IDSECTOR结构信息

可选在参数中指定硬盘序�?不指定参数时自动获取可用序号,

[返回对象:syshdinfObject](#syshdinfObject)

## syshdinfObject 成员列表

### syshdinfObject.sFirmwareRev

硬盘硬件版本

请自行使用string.trim函数去掉首尾空格

### syshdinfObject.sModelNumber

硬盘型号

请自行使用string.trim函数去掉首尾空格

### syshdinfObject.sSerialNumber

硬盘生产序号

请自行使用string.trim函数去掉首尾空格

### syshdinfObject.ulTotalAddressableSectors

```aardio aardio
ulTotalAddressableSectors

```

### syshdinfObject.wBufferSize

缓冲大小

### syshdinfObject.wBufferType

缓冲类型

### syshdinfObject.wCapabilities

支持功能

不同的二进制位表示硬盘是否支持指定功�?
### syshdinfObject.wGenConfig

基本信息�?
### syshdinfObject.wNumCyls

柱面�?
### syshdinfObject.wNumHeads

磁头�?
### syshdinfObject.wNumSectorsPerTrack

每磁道扇区数

### syshdinfObject.wReserved2

保留

### syshdinfObject.wUltraDMA

Ultra DMA支持能力

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/sys/hd.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/sys/hd.md')

