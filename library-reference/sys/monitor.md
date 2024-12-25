[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# sys.monitor 库模块帮助文�?
## sys.monitor 成员列表

显示器函数库�?
相关�? com.monitor, sys.display, sys.ddcci �?
### sys.monitor.changeMode

修改显示器设�?
### sys.monitor.changeMode(mode,flags,deviceName)

修改显示器设�?
参数 @mode 指定 DEVMODE\_DISPLAY\_DEVICE 结构体，

@mode 也可以传一个普通表，仅指定部分需要更新的结构体字段。也可以使用 sys.monitor.eachMode 获取的结构体作为参数 @mode�?
省略 @mode �?@flags 恢复默认设置�?
@flags 可省�?该值可使用 _CDS_ 前缀的常量指�?默认�?0�?
@deviceName 指定显示器名，省略则设置默认显示器�?
可用 sys.monitor.eachDevice 获取可用 deviceName

用法请参�?API 函数 ::User32.ChangeDisplaySettingsExW 的文�?
### sys.monitor.eachDevice()

[返回对象:DISPLAYDEVICEObject](#DISPLAYDEVICEObject)

### sys.monitor.eachDevice(flags,deviceName)

```aardio aardio
for( dev in sys.monitor.eachDevice(1) ){
    /*如果不指定参数则遍历所有显示适配器�?如果参数 @2 指定适配置的设备名（ eachMode �?eachDevice 遍历返回对象�?deviceName 字段），
则遍历该适配器上的所有显示器设备�?
如果指定了参�?@2 ，且参数 @1 值为 1�?则遍历返回对象的 deviceId2 字段为设�?ID�?/
}

```

### sys.monitor.eachInfo()

[返回对象:MONITORINFOObject](#MONITORINFOObject)

### sys.monitor.eachInfo(hdc,rcClip)

```aardio aardio
for( hMonitor,monitorInfo in sys.monitor.eachInfo() ){
    /*用法请参考此函数源码*/
}

```

### sys.monitor.eachMode()

[返回对象:DEVMODEDISPLAYDEVICEObject](#DEVMODEDISPLAYDEVICEObject)

### sys.monitor.eachMode(flags,deviceName)

```aardio aardio
for( devMode in sys.monitor.eachMode() ){
    if( devMode.pelsWidth > (devMode.pelsWidth > devMode.pelsHeight ? 640 : 480) ){
            /*遍历显示器支持的模式�?所有参考可选，用法请参考此函数源码�?可通过 sys.monitor.eachDevice 获取可用 deviceName*/
    }
}

```

### sys.monitor.getInfo()

[返回对象:MONITORINFOObject](#MONITORINFOObject)

### sys.monitor.getInfo(hMonitor)

参数为显示设备句�?
返回显示器信�?
### sys.monitor.getInfoFromPoint()

[返回对象:MONITORINFOObject](#MONITORINFOObject)

### sys.monitor.getInfoFromPoint(x,y)

获取指定坐标所在显示器信息,\\所有参数可�?
### sys.monitor.getInfoFromWindow()

[返回对象:MONITORINFOObject](#MONITORINFOObject)

### sys.monitor.getInfoFromWindow(窗口句柄)

获取窗口所在显示器信息,\\所有参数可�?
## DEVMODEDISPLAYDEVICEObject 成员列表

### DEVMODEDISPLAYDEVICEObject.bitsPerPel

像素位宽

### DEVMODEDISPLAYDEVICEObject.displayFrequency

刷新频率

### DEVMODEDISPLAYDEVICEObject.displayOrientation

显示方向,参考\_DMDO\_ 前缀常量

### DEVMODEDISPLAYDEVICEObject.pelsHeight

像素高度

### DEVMODEDISPLAYDEVICEObject.pelsWidth

像素宽度

## DISPLAYDEVICEObject 成员列表

### DISPLAYDEVICEObject.deviceId

设备 ID�?
典型的格式为 \\.\\DISPLAY###

### DISPLAYDEVICEObject.deviceId2

设备 ID�?
仅保�?deviceId 字段�? 部分�?
可通用�?com.monitor 的设�?ID 参数�?
### DISPLAYDEVICEObject.deviceKey

设备在注册表中的键路径，主要用于获取和配置设备的详细信息�?
### DISPLAYDEVICEObject.deviceName

适配器设备或监视器设备的设备�?
### DISPLAYDEVICEObject.deviceString

显示适配器或显示监视器的描述

### DISPLAYDEVICEObject.stateFlags

设备状态标志�?
\_DISPLAY\_DEVICE 前缀常量数值或这些数值的组合

## MONITORINFOObject 成员列表

### MONITORINFOObject.deviceName

�?sys.monitor.getInfoEx �?sys.monitor.eachInfo 函数会返回该�?
### MONITORINFOObject.eachDevice()

```aardio aardio
for dev in MONITORINFOObject.eachDevice() {
    /*遍历此适配器上的所有显示器设备�?则遍历返回对象的 deviceId2 字段为设�?ID�?/
}

[返回对象:DISPLAYDEVICEObject](#DISPLAYDEVICEObject)

```

### MONITORINFOObject.flags

该值为1时为主显示器

### MONITORINFOObject.rcMonitor

显示器的在屏幕坐标系中的矩形

[返回对象:rectObject](../global/_.html#rectObject)

### MONITORINFOObject.rcWork

显示器的工作区域

[返回对象:rectObject](../global/_.html#rectObject)

### 自动完成常量

\_CDS\_DISABLE\_UNSAFE\_MODES=0x200

\_CDS\_ENABLE\_UNSAFE\_MODES=0x100

\_CDS\_FULLSCREEN=4

\_CDS\_GLOBAL=8

\_CDS\_NORESET=0x10000000

\_CDS\_RESET=0x40000000

\_CDS\_RESET\_EX=0x20000000

\_CDS\_SET\_PRIMARY=0x10

\_CDS\_TEST=2

\_CDS\_UPDATEREGISTRY=1

\_CDS\_VIDEOPARAMETERS=0x20

\_DISPLAY\_DEVICE\_ACTIVE=1

\_DISPLAY\_DEVICE\_MIRRORING\_DRIVER=8

\_DISPLAY\_DEVICE\_MODESPRUNED=0x8000000

\_DISPLAY\_DEVICE\_PRIMARY\_DEVICE=4

\_DISPLAY\_DEVICE\_REMOVABLE=0x20

\_DISPLAY\_DEVICE\_VGA\_COMPATIBLE=0x10

\_DMDO\_180=2

\_DMDO\_270=3

\_DMDO\_90=1

\_DMDO\_DEFAULT=0

\_EDS\_RAWMODE=0x2

\_ENUM\_CURRENT\_SETTINGS=-1

\_ENUM\_REGISTRY\_SETTINGS=-2

\_MONITORINFOF\_PRIMARY=1

\_MONITOR\_DEFAULTTONEAREST=2

\_MONITOR\_DEFAULTTONULL=0

\_MONITOR\_DEFAULTTOPRIMARY=1

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/sys/monitor.md)

