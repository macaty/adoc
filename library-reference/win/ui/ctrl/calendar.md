[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# win.ui.ctrl.calendar 库模块帮助文�?
## win.ui.ctrl 成员列表

### win.ui.ctrl.calendar()

日历控件

[返回对象:calendarObject](#calendarObject)

## calendarObject 成员列表

### calendarObject.\_parentForm

创建该控件的父窗口（win.form对象�?

设计时窗体容器是所有拖放在窗体上的控件�?\_parentForm,

即使窗口移除子窗口样式、更改父子关系，或以 orphanWindow显示,

控件�?\_parentForm 始终都不会改�?
[返回对象:winform](../_.html#winform)

### calendarObject.bottom

底部坐标

### calendarObject.capture

是否捕获全局鼠标消息

### calendarObject.className

运行时类�?
### calendarObject.close()

关闭控件窗口

### calendarObject.cls

设计时类�?
### calendarObject.disabled

是否禁用

### calendarObject.getClientRect()

控件客户区块位置(::RECT结构�?

[返回对象:rectObject](../../../global/_.html#rectObject)

### calendarObject.getFont()

控件字体(::LOGFONT结构�?

[返回对象:logfontObject](#logfontObject)

### calendarObject.getParent()

返回父窗�?
[返回对象:staticObject](static.html#staticObject)

### calendarObject.getPos()

返回相对坐标,�?�?
x,y,cx,cy=win.getPos(hwnd)

### calendarObject.getRange()

返回两个time()对象:时间范围下限,时间范围上限

如果未调用setRange()指定上限或下�?相应值返回为�?
### calendarObject.getRect()

控件区块位置(::RECT结构�?

### calendarObject.getRect(true)

控件屏幕区块位置(::RECT结构�?

### calendarObject.height

高度

### calendarObject.hide

控件是否隐藏

### calendarObject.hwnd

控件句柄

### calendarObject.id

控件ID

### calendarObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/)

使窗口绘图区无效

### calendarObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/,0)

使窗口绘图区无效

不刷新背�?
### calendarObject.left

左侧坐标

### calendarObject.modifyStyle(remove,add,swpFlags)

修改窗口样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### calendarObject.modifyStyleEx(remove,add,swpFlags)

修改窗口扩展样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS\_EX_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS\_EX_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### calendarObject.postMessage(msg,wParam,lParam)

投递窗口消息到消息队列�?
此函数用法请参�?::User32.PostMessage

### calendarObject.redraw()

刷新

### calendarObject.right

右侧坐标

### calendarObject.sendMessage(msg,wParam,lParam)

发送窗口消�?
此函数用法请参�?::User32.SendMessage

### calendarObject.setFocus()

设置焦点

### calendarObject.setFont(指定字体)

指定LOGFONT字体对象,或逻辑字体句柄

### calendarObject.setFont(混入字体属�?

```aardio aardio
calendarObject.setFont(point=10;name="宋体");

```

### calendarObject.setParent(控件对象)

改变父窗�?
### calendarObject.setPos(x坐标,y坐标,�?�?插入位置,参数)

调整窗口位置或排�?所有参数可�?
同时指定x,y坐标则移动位�?
同时指定宽高则改变大�?
指定插入位置(句柄或\_HWND前缀常量)则调整Z�?
### calendarObject.setRange(时间下限,时间上限)

设置时间范围,参数为time()对象

可省略其中一个参�?仅指定下限或仅指定上�?
### calendarObject.setRect(rc)

设置控件区块位置(::RECT结构�?

### calendarObject.setRect(rc,true)

设置控件屏幕区块位置(::RECT结构�?

### calendarObject.show(true)

显示控件

### calendarObject.text

控件文本

### calendarObject.theme

外观主题,例如

winform.button.theme = "Explorer"

winform.button.theme = false

### calendarObject.time

获取或设置时�?
[返回对象:timeObject](../../../time/_.html#timeObject)

### calendarObject.top

顶部坐标

### calendarObject.update()

重绘invalidate函数指定的区�?
### calendarObject.width

宽度

### 自动完成常量

\_MCM\_FIRST=0x1000

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/win/ui/ctrl/calendar.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/win/ui/ctrl/calendar.md')

