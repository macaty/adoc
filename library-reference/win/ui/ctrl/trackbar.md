[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# win.ui.ctrl.trackbar 库模块帮助文�?
## win.ui.ctrl 成员列表

### win.ui.ctrl.trackbar()

跟踪条控�?
XP 系统不支持透明背景，之后的系统都支�?
[返回对象:trackbarObject](#trackbarObject)

## trackbarObject 成员列表

### trackbarObject.\_parentForm

创建该控件的父窗口（win.form对象�?

设计时窗体容器是所有拖放在窗体上的控件�?\_parentForm,

即使窗口移除子窗口样式、更改父子关系，或以 orphanWindow显示,

控件�?\_parentForm 始终都不会改�?
[返回对象:winform](../_.html#winform)

### trackbarObject.bottom

底部坐标

### trackbarObject.capture

是否捕获全局鼠标消息

### trackbarObject.className

运行时类�?
### trackbarObject.close()

关闭控件�?
### trackbarObject.cls

设计时类�?
### trackbarObject.disabled

是否禁用

### trackbarObject.getClientRect()

控件客户区块位置(::RECT结构�?

[返回对象:rectObject](../../../global/_.html#rectObject)

### trackbarObject.getFont()

控件字体(::LOGFONT结构�?

[返回对象:logfontObject](#logfontObject)

### trackbarObject.getNotifyCustomDraw()

[返回对象:NMCUSTOMDRAWObject](#NMCUSTOMDRAWObject)

### trackbarObject.getNotifyCustomDraw(code,ptr)

NM\_CUSTOMDRAW通知消息返回NMLVCUSTOMDRAW结构�?
### trackbarObject.getParent()

返回父窗�?
[返回对象:staticObject](static.html#staticObject)

### trackbarObject.getPos()

返回相对坐标,�?�?
x,y,cx,cy=win.getPos(hwnd)

### trackbarObject.getRect()

控件区块位置(::RECT结构�?

### trackbarObject.getRect(true)

控件屏幕区块位置(::RECT结构�?

### trackbarObject.height

高度

### trackbarObject.hide

控件是否隐藏

### trackbarObject.hwnd

控件句柄

### trackbarObject.id

控件ID

### trackbarObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/)

使窗口绘图区无效

### trackbarObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/,0)

使窗口绘图区无效

不刷新背�?
### trackbarObject.left

左侧坐标

### trackbarObject.max

最大�?注意不能大于0xFFFF,不要使用负数

### trackbarObject.min

最小�?注意不能大于0xFFFF,不要使用负数

### trackbarObject.modifyStyle(remove,add,swpFlags)

修改窗口样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### trackbarObject.modifyStyleEx(remove,add,swpFlags)

修改窗口扩展样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS\_EX_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS\_EX_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### trackbarObject.pos

滑块当前刻度,注意不能大于0xFFFF,不要使用负数

### trackbarObject.postMessage(msg,wParam,lParam)

投递窗口消息到消息队列�?
此函数用法请参�?::User32.PostMessage

### trackbarObject.redraw()

刷新

### trackbarObject.right

右侧坐标

### trackbarObject.sendMessage(msg,wParam,lParam)

发送窗口消�?
此函数用法请参�?::User32.SendMessage

### trackbarObject.setFocus()

设置焦点

### trackbarObject.setFont(指定字体)

指定LOGFONT字体对象,或逻辑字体句柄

### trackbarObject.setFont(混入字体属�?

```aardio aardio
trackbarObject.setFont(point=10;name="宋体");

```

### trackbarObject.setFrequency(2)

刻度标记间隔

必须在样式中指定自动刻度标记

### trackbarObject.setParent(控件对象)

改变父窗�?
### trackbarObject.setPos(x坐标,y坐标,�?�?插入位置,参数)

调整窗口位置或排�?所有参数可�?
同时指定x,y坐标则移动位�?
同时指定宽高则改变大�?
指定插入位置(句柄或\_HWND前缀常量)则调整Z�?
### trackbarObject.setRange(最小刻�?最大刻�?

设置最大最小刻�?注意不能大于0xFFFF,不要使用负数

### trackbarObject.setRect(rc)

设置控件区块位置(::RECT结构�?

### trackbarObject.setRect(rc,true)

设置控件屏幕区块位置(::RECT结构�?

### trackbarObject.setSel(起始刻度,结束刻度)

设置选区

### trackbarObject.setTick(刻度)

显示设置刻度标记位置

### trackbarObject.show(true)

显示控件

### trackbarObject.theme

外观主题,例如

winform.button.theme = "Explorer"

winform.button.theme = false

### trackbarObject.threadCallable()

开启此控件的跨线程调用功能

### trackbarObject.tooltip

提示文本,只写属�?

值如果不是指针会自动调用 tostring 函数转为字符�?

可用于在 oncommand 事件中修改提示文�?
### trackbarObject.top

顶部坐标

### trackbarObject.update()

重绘invalidate函数指定的区�?
### trackbarObject.width

宽度

## NMCUSTOMDRAWObject 成员列表

### NMCUSTOMDRAWObject.dwDrawStage

绘图状�?
### NMCUSTOMDRAWObject.dwItemSpec

行序�?
### NMCUSTOMDRAWObject.hdc

设置句柄

### NMCUSTOMDRAWObject.hdr

[返回对象:nmhdrObject](#nmhdrObject)

### NMCUSTOMDRAWObject.lItemlParam

自定义数据，LPARAM 参数

### NMCUSTOMDRAWObject.rc

[返回对象:rectObject](../../../global/_.html#rectObject)

### NMCUSTOMDRAWObject.uItemState

状态值，例如 \_CDIS\_FOCUS

### NMCUSTOMDRAWObject.update()

更新数据

### 自动完成常量

\_CCM\_GETUNICODEFORMAT=0x2006

\_CCM\_SETUNICODEFORMAT=0x2005

\_TBM\_CLEARSEL=0x413

\_TBM\_CLEARTICS=0x409

\_TBM\_GETBUDDY=0x421

\_TBM\_GETCHANNELRECT=0x41A

\_TBM\_GETLINESIZE=0x418

\_TBM\_GETNUMTICS=0x410

\_TBM\_GETPAGESIZE=0x416

\_TBM\_GETPOS=0x400

\_TBM\_GETPTICS=0x40E

\_TBM\_GETRANGEMAX=0x402

\_TBM\_GETRANGEMIN=0x401

\_TBM\_GETSELEND=0x412

\_TBM\_GETSELSTART=0x411

\_TBM\_GETTHUMBLENGTH=0x41C

\_TBM\_GETTHUMBRECT=0x419

\_TBM\_GETTIC=0x403

\_TBM\_GETTICPOS=0x40F

\_TBM\_GETTOOLTIPS=0x41E

\_TBM\_GETUNICODEFORMAT=0x2006

\_TBM\_SETBUDDY=0x420

\_TBM\_SETLINESIZE=0x417

\_TBM\_SETPAGESIZE=0x415

\_TBM\_SETPOS=0x405

\_TBM\_SETPOSNOTIFY=0x422

\_TBM\_SETRANGE=0x406

\_TBM\_SETRANGEMAX=0x408

\_TBM\_SETRANGEMIN=0x407

\_TBM\_SETSEL=0x40A

\_TBM\_SETSELEND=0x40C

\_TBM\_SETSELSTART=0x40B

\_TBM\_SETTHUMBLENGTH=0x41B

\_TBM\_SETTIC=0x404

\_TBM\_SETTICFREQ=0x414

\_TBM\_SETTIPSIDE=0x41F

\_TBM\_SETTOOLTIPS=0x41D

\_TBM\_SETUNICODEFORMAT=0x2005

\_TBS\_AUTOTICKS=0x1

\_TBS\_BOTH=0x8

\_TBS\_BOTTOM=0x0

\_TBS\_DOWNISLEFT=0x400

\_TBS\_ENABLESELRANGE=0x20

\_TBS\_FIXEDLENGTH=0x40

\_TBS\_HORZ=0x0

\_TBS\_LEFT=0x4

\_TBS\_NOTHUMB=0x80

\_TBS\_NOTICKS=0x10

\_TBS\_NOTIFYBEFOREMOVE=0x800

\_TBS\_REVERSED=0x200

\_TBS\_RIGHT=0x0

\_TBS\_TOOLTIPS=0x100

\_TBS\_TOP=0x4

\_TBS\_TRANSPARENTBKGND=0x1000

\_TBS\_VERT=0x2

\_TB\_BOTTOM=0x7

\_TB\_ENDTRACK=0x8

\_TB\_LINEDOWN=0x1

\_TB\_LINEUP=0x0

\_TB\_PAGEDOWN=0x3

\_TB\_PAGEUP=0x2

\_TB\_THUMBPOSITION=0x4

\_TB\_THUMBTRACK=0x5

\_TB\_TOP=0x6

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/win/ui/ctrl/trackbar.md)

