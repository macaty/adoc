[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# sys.ddcci 库模块帮助文�?
## sys 成员列表

### sys.ddcci()

[返回对象:SysDdcciObject](#SysDdcciObject)

### sys.ddcci(hpm,description)

创建显示器控制对象，

@hpm 为物理显示器句柄,

@description 为显示器描述，可选参�?
## sys.ddcci 成员列表

DDC/CI（Display Data Channel Command Interface�?
用于控制显示器，不是所有显示器都支�?DDC/CI

创建显示器控制对�?
### sys.ddcci.each()

```aardio aardio
for ddcci in sys.ddcci.each() {
    /*遍历所有物理显示器�?ddcci 为控制该显示器的 sys.ddcci 对象*/
}

[返回对象:SysDdcciObject](#SysDdcciObject)

```

### sys.ddcci.getPhysicalMonitors

返回所有物理显示器句柄数组

### sys.ddcci.getPhysicalMonitors()

返回所有物理显示器句柄数组

### sys.ddcci.getPhysicalMonitors(hMonitor)

返回 @hMonitor 指定句柄的显示器指向的物理显示器句柄数组,

注意参数 @hMonitor 指定显示器句柄，并非物理显示器句�?
## SysDdcciObject 成员列表

### SysDdcciObject.capabilities

返回描述显示器支持功能的表对�?
### SysDdcciObject.description

显示器描�?
### SysDdcciObject.destroy()

释放对象�?
如果没有调用此函数，则回收对象时自动调用�?
### SysDdcciObject.getBrightness()

获取亮度，返�?个值：

当前亮度，最小值，最大�?
### SysDdcciObject.getColorTemperature()

获取色温

### SysDdcciObject.getContrast()

获取对比度，返回3个值：

当前亮度，最小值，最大�?
### SysDdcciObject.getFeature(vcpCode)

读取设置�?
@vcpCode 为控制代�?
### SysDdcciObject.getInputSource()

获取输入�?
### SysDdcciObject.getPowerMode()

获取电源状�?
### SysDdcciObject.hasFeature(vcpCode)

是否支持 @vcpCode 指定的控制代�?
支持则返回包含可设置值的数组,数组可能为空,

否则返回 null

### SysDdcciObject.reset()

重置设置

### SysDdcciObject.resetColor()

重置颜色设置

### SysDdcciObject.save()

保存设置

### SysDdcciObject.setBrightness(value)

设置亮度

### SysDdcciObject.setColorTemperature(value)

设置色温

### SysDdcciObject.setContrast(value)

设置对比�?
### SysDdcciObject.setFeature(vcpCode,value)

写入设置�?
@vcpCode 为控制代�?@value 为新的设置�?
### SysDdcciObject.setInputSource(inputSource)

修改输入�?

@inputSource 用数值指定输入源

### SysDdcciObject.setPowerMode(mode)

修改电源状�?

@mode �?表示打开屏幕�?
@mode �?5 �?4 表示关闭屏幕

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/sys/ddcci.md)

