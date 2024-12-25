[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# win.ui.ctrl.scrollbar 库模块帮助文�?
## win.ui.ctrl 成员列表

### win.ui.ctrl.scrollbar()

滚动条控�?
[返回对象:scrollbarObject](#scrollbarObject)

## scrollbarObject 成员列表

### scrollbarObject.\_parentForm

创建该控件的父窗口（win.form对象�?

设计时窗体容器是所有拖放在窗体上的控件�?\_parentForm,

即使窗口移除子窗口样式、更改父子关系，或以 orphanWindow显示,

控件�?\_parentForm 始终都不会改�?
[返回对象:winform](../_.html#winform)

### scrollbarObject.adjust

```aardio aardio
scrollbarObject.adjust = function( cx,cy,wParam ) {
    _/*窗口改变大小时触发此函数*/
};

```

### scrollbarObject.adjustWindow()

仅绑定窗口的滚动条此函数有效,\\窗口调整大小时必须使用此函数重新滚动窗口到滚动条当前位置

### scrollbarObject.bottom

底部坐标

### scrollbarObject.capture

是否捕获全局鼠标消息

### scrollbarObject.className

运行时类�?
### scrollbarObject.close()

关闭控件窗口

### scrollbarObject.cls

设计时类�?
### scrollbarObject.disabled

是否禁用

### scrollbarObject.enable( _ESB_ )

激活一个或两个滚动条箭头或是使其失�?
### scrollbarObject.getClientRect()

控件客户区块位置(::RECT结构�?

[返回对象:rectObject](../../../global/_.html#rectObject)

### scrollbarObject.getFont()

控件字体(::LOGFONT结构�?

[返回对象:logfontObject](#logfontObject)

### scrollbarObject.getInfo()

返回滚动条信�?
### scrollbarObject.getParent()

返回父窗�?
[返回对象:scrollbarObject](#scrollbarObject)

### scrollbarObject.getPos()

返回相对坐标,�?�?
x,y,cx,cy=win.getPos(hwnd)

### scrollbarObject.getRange()

返回 4 个数�?
分别�?min,max,page,current,

min 为滚动条范围最小�?

max 为滚动条范围最大�?

page为分页大�?

current 为滚动条当前位置

### scrollbarObject.getRect()

控件区块位置(::RECT结构�?

### scrollbarObject.getRect(true)

控件屏幕区块位置(::RECT结构�?

### scrollbarObject.height

高度

### scrollbarObject.hide

控件是否隐藏

### scrollbarObject.hwnd

控件句柄

### scrollbarObject.id

控件ID

### scrollbarObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/)

使窗口绘图区无效

### scrollbarObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/,0)

使窗口绘图区无效

不刷新背�?
### scrollbarObject.left

左侧坐标

### scrollbarObject.line

行高

### scrollbarObject.modifyStyle(remove,add,swpFlags)

修改窗口样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### scrollbarObject.modifyStyleEx(remove,add,swpFlags)

修改窗口扩展样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS\_EX_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS\_EX_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### scrollbarObject.pos

获取或设置滚动按钮的当前位置

如果赋值为负数、可禁止窗口重绘

### scrollbarObject.postMessage(msg,wParam,lParam)

投递窗口消息到消息队列�?
此函数用法请参�?::User32.PostMessage

### scrollbarObject.redraw()

刷新

### scrollbarObject.right

右侧坐标

### scrollbarObject.scrollMessage

滚动条消息ID

水平滚动条为 \_WM\_HSCROLL,

垂直滚动条为 \_WM\_HSCROLL

### scrollbarObject.scrollWindowTo(pos,rect,clipRect)

仅绑定窗口的滚动条此函数有效,

@pos 参数指定滚动条绝对位�?

可选用 @rect 传入 ::RECT 结构体指定滚动区�?,

可选用 @clipRect 传入 ::RECT 结构体指定剪切区�?
### scrollbarObject.sendMessage(msg,wParam,lParam)

发送窗口消�?
此函数用法请参�?::User32.SendMessage

### scrollbarObject.setFocus()

设置焦点

### scrollbarObject.setFont(指定字体)

指定LOGFONT字体对象,或逻辑字体句柄

### scrollbarObject.setFont(混入字体属�?

```aardio aardio
scrollbarObject.setFont(point=10;name="宋体");

```

### scrollbarObject.setInfo()

```aardio aardio
scrollbarObject.setInfo(
    fMask = fMask;
    min = min;
    max = max;
    page = page;
    pos = pos;
    trackPos = trackPos;
)

```

### scrollbarObject.setParent(控件对象)

改变父窗�?
### scrollbarObject.setPos(x坐标,y坐标,�?�?插入位置,参数)

调整窗口位置或排�?所有参数可�?
同时指定x,y坐标则移动位�?
同时指定宽高则改变大�?
指定插入位置(句柄或\_HWND前缀常量)则调整Z�?
### scrollbarObject.setRange

设置滚动条范�?
### scrollbarObject.setRange(min,max,page,redraw)

设置滚动条范围，参数�?
@min 为滚动条范围最小�?

@max 为滚动条范围最大�?

@page为分页大�?

@redraw 是否刷新�?
### scrollbarObject.setRect(rc)

设置控件区块位置(::RECT结构�?

### scrollbarObject.setRect(rc,true)

设置控件屏幕区块位置(::RECT结构�?

### scrollbarObject.show(true)

显示控件

### scrollbarObject.theme

外观主题,例如

winform.button.theme = "Explorer"

winform.button.theme = false

### scrollbarObject.top

顶部坐标

### scrollbarObject.update()

重绘invalidate函数指定的区�?
### scrollbarObject.updateWheelLines()

返回系统设置的鼠标滚轮滚动行�?

并更�?wheelLines 的�?
### scrollbarObject.wheelLines

鼠标滚轮滚动行数,默认值为 3

调用 updateWheelLines 函数可获取系统设置并更新该�?
### scrollbarObject.width

宽度

### 自动完成常量

\_SIF\_ALL=0x17

\_SIF\_DISABLENOSCROLL=0x8

\_SIF\_PAGE=0x2

\_SIF\_POS=0x4

\_SIF\_RANGE=0x1

\_SIF\_TRACKPOS=0x10

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/win/ui/ctrl/scrollbar.md)

