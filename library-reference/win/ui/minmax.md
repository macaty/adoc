[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# win.ui.minmax 库模块帮助文�?
## minmaxSettingObject 成员列表

### minmaxSettingObject.argsMax

用于限制窗口最大宽�?

修改此属性与修改 win.ui.minmax 的构造参数作用一�?
[返回对象:sizeObject](#sizeObject)

### minmaxSettingObject.argsMin

用于限制窗口最小宽�?

修改此属性与修改 win.ui.minmax 的构造参数作用一�?
[返回对象:sizeObject](#sizeObject)

### minmaxSettingObject.maxPosition

自动维护此属性请不要修改,应修�?argsMax

[返回对象:pointObject](#pointObject)

### minmaxSettingObject.maxSize

自动维护此属性请不要修改,应修�?argsMax

[返回对象:pointObject](#pointObject)

### minmaxSettingObject.maxTrackSize

自动维护此属性请不要修改,应修�?argsMax

[返回对象:pointObject](#pointObject)

### minmaxSettingObject.minTrackSize

自动维护此属性请不要修改,应修�?argsMin

[返回对象:pointObject](#pointObject)

### minmaxSettingObject.updateMinMaxInfo()

重新计算窗口缩放大小范围

[返回对象:minmaxSettingObject](#minmaxSettingObject)

## win.ui 成员列表

### win.ui.minmax

窗口缩放范围设置�?
一个窗口只�?
创建窗口缩放范围设置�?
一个窗口只能创建一�?重复调用将重用并返回第一次创建的设置�?
### win.ui.minmax()

[返回对象:minmaxSettingObject](#minmaxSettingObject)

### win.ui.minmax(winform,最小宽�?最小高�?最大宽�?最大高�?

除第一个参数以�?其他参数可�?
默认最小为当前窗口大小,最大为最大化大小

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/win/ui/minmax.md)

