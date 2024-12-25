[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# sys.cpu 库模块帮助文�?
## sys.cpu 成员列表

### sys.cpu.getBrand()

返回CPU商标信息

### sys.cpu.getFrequence()

返回表示 CPU 频率的数�?�?MHz 为单�?
### sys.cpu.getFrequence(true)

返回表示 CPU 频率的友好格式的字符�?

单位: GHz 小数位数�?

### sys.cpu.getInfo

```aardio aardio
sys.cpu.getInfo(1/*查询索引*/,{ INT eax;INT ebx;INT ecx;INT edx } )

```

### sys.cpu.getInfo()

[返回对象:sysCpuInfoObject](#sysCpuInfoObject)

### sys.cpu.getInfoByWmi()

使用 WMI 接口�?win32\_processor 查询处理器信�?
参�?[https://docs.microsoft.com/en-us/windows/win32/cimwin32prov/win32-processor](https://docs.microsoft.com/en-us/windows/win32/cimwin32prov/win32-processor)

[返回对象:sysCpuWmiInfoObject](#sysCpuWmiInfoObject)

### sys.cpu.getMaxExtFunction()

CPU的扩展信息最大查询索�?
### sys.cpu.getVender()

返回制造商信息,以及CPU基础信息最大查询索�?
Intel会返�?GenuineIntel",

AMD会返�?AuthenticAMD"

## sysCpuInfoObject 成员列表

### sysCpuInfoObject.eax

整数

### sysCpuInfoObject.ebx

整数

### sysCpuInfoObject.ecx

整数

### sysCpuInfoObject.edx

整数

## sysCpuWmiInfoObject 成员列表

### sysCpuWmiInfoObject.?

参�?[https://docs.microsoft.com/en-us/windows/win32/cimwin32prov/win32-processor](https://docs.microsoft.com/en-us/windows/win32/cimwin32prov/win32-processor)

### sysCpuWmiInfoObject.AddressWidth

CPU 位宽,值为 32 �?64

### sysCpuWmiInfoObject.Architecture

指令集架�?x86 值为 0,x64 值为 9

### sysCpuWmiInfoObject.CurrentClockSpeed

CPU 当前速度,单位 MHz,

该值除 1000 可换算为单位 GHz

使用 math.round 可以限定小数位数

### sysCpuWmiInfoObject.DeviceID

设备 ID

### sysCpuWmiInfoObject.Manufacturer

生产厂商,例如"GenuineIntel"

### sysCpuWmiInfoObject.MaxClockSpeed

CPU 最大速度,单位 MHz,

该值除 1000 可换算为单位 GHz

### sysCpuWmiInfoObject.Name

设备�?
### sysCpuWmiInfoObject.NumberOfCores

CPU 核心�?
### sysCpuWmiInfoObject.NumberOfLogicalProcessors

CPU 逻辑核心�?
[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/sys/cpu.md)

