[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# win.ui.ctrl.progress 库模块帮助文�?
## win.ui.ctrl 成员列表

### win.ui.ctrl.progress

进度条控�?
### win.ui.ctrl.progress()

进度条控�?
[返回对象:progressObject](#progressObject)

## progressObject 成员列表

### progressObject.\_parentForm

创建该控件的父窗口（win.form对象�?

设计时窗体容器是所有拖放在窗体上的控件�?\_parentForm,

即使窗口移除子窗口样式、更改父子关系，或以 orphanWindow显示,

控件�?\_parentForm 始终都不会改�?
[返回对象:winform](../_.html#winform)

### progressObject.bottom

底部坐标

### progressObject.capture

是否捕获全局鼠标消息

### progressObject.close()

关闭控件�?
### progressObject.delta(偏移�?

修改当前进度,参数指定相对于当前进度的偏移�?
### progressObject.disabled

是否禁用

### progressObject.getClientRect()

控件客户区块位置(::RECT结构�?

[返回对象:rectObject](../../../global/_.html#rectObject)

### progressObject.getParent()

返回父窗�?
[返回对象:staticObject](static.html#staticObject)

### progressObject.getPos()

返回相对坐标,�?�?
x,y,cx,cy=win.getPos(hwnd)

### progressObject.getRect()

控件区块位置(::RECT结构�?

### progressObject.getRect(true)

控件屏幕区块位置(::RECT结构�?

### progressObject.height

高度

### progressObject.hide

控件是否隐藏

### progressObject.hwnd

控件句柄

### progressObject.id

控件ID

### progressObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/)

使窗口绘图区无效

### progressObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/,0)

使窗口绘图区无效

不刷新背�?
### progressObject.left

左侧坐标

### progressObject.max

最大�?注意不能大于0xFFFF,不要使用负数

### progressObject.min

最小�?注意不能大于0xFFFF,不要使用负数

### progressObject.modifyStyle(remove,add,swpFlags)

修改窗口样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### progressObject.modifyStyleEx(remove,add,swpFlags)

修改窗口扩展样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS\_EX_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS\_EX_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### progressObject.orphanWindow()

使控件脱离原来的窗口,可以显示在父窗口外面,

但仍然显示在原来的位�?继续如影随形的跟随父窗口移动或改变大�?

控件原来的固定边距等参数仍然有效

### progressObject.pos

进度条当前�?不能大于0xFFFF,不要使用负数

### progressObject.redraw()

刷新

### progressObject.right

右侧坐标

### progressObject.setFocus()

设置焦点

### progressObject.setParent(控件对象)

改变父窗�?
### progressObject.setPos(x坐标,y坐标,�?�?插入位置,参数)

调整窗口位置或排�?所有参数可�?
同时指定x,y坐标则移动位�?
同时指定宽高则改变大�?
指定插入位置(句柄或\_HWND前缀常量)则调整Z�?
### progressObject.setRange(最小�?最大�?

设置进度条最大�?最小�?
注意值不能大�?xFFFF,不要使用负数

### progressObject.setRect(rc)

设置控件区块位置(::RECT结构�?

### progressObject.setRect(rc,true)

设置控件屏幕区块位置(::RECT结构�?

### progressObject.show(true)

显示控件

### progressObject.startProgress()

显示进条,并显示循环滚动进度的动画,

可选在参数中指定动画间隔时,以毫秒为单位

### progressObject.step

设置stepIt()函数的步进增�?
默认�?0

### progressObject.stepIt()

进度条前进一个增量，最出最大值时设为最小值�?
返回步进前位�?
### progressObject.stopProgress()

停止显示循环滚动进度动画,隐藏进度�?
### progressObject.theme

外观主题,例如

winform.button.theme = "Explorer"

winform.button.theme = false

### progressObject.threadCallable()

开启此控件的跨线程调用功能

### progressObject.top

顶部坐标

### progressObject.update()

重绘invalidate函数指定的区�?
### progressObject.width

宽度

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/win/ui/ctrl/progress.md)

