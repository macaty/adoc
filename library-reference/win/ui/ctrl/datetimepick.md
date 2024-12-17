[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# win.ui.ctrl.datetimepick 库模块帮助文�?
## win.ui.ctrl 成员列表

### win.ui.ctrl.datetimepick()

时间控件

[返回对象:datetimepickObject](#datetimepickObject)

## datetimepickObject 成员列表

### datetimepickObject.\_parentForm

创建该控件的父窗口（win.form对象�?

设计时窗体容器是所有拖放在窗体上的控件�?\_parentForm,

即使窗口移除子窗口样式、更改父子关系，或以 orphanWindow显示,

控件�?\_parentForm 始终都不会改�?
[返回对象:winform](../_.html#winform)

### datetimepickObject.bottom

底部坐标

### datetimepickObject.capture

是否捕获全局鼠标消息

### datetimepickObject.checked

或取设置控件选中状�?
创建控件的参数中指定style=\_DTS\_SHOWNONE

### datetimepickObject.className

运行时类�?
### datetimepickObject.clientRect

获取控件客户区块位置(::RECT结构�?

### datetimepickObject.close()

关闭控件窗口

### datetimepickObject.cls

设计时类�?
### datetimepickObject.disabled

是否禁用

### datetimepickObject.getClientRect()

控件客户区块位置(::RECT结构�?

[返回对象:rectObject](../../../global/_.html#rectObject)

### datetimepickObject.getFont()

控件字体(::LOGFONT结构�?

[返回对象:logfontObject](#logfontObject)

### datetimepickObject.getParent()

返回父窗�?
[返回对象:staticObject](static.html#staticObject)

### datetimepickObject.getPos()

返回相对坐标,�?�?
x,y,cx,cy=win.getPos(hwnd)

### datetimepickObject.getRange()

返回两个time()对象:时间范围下限,时间范围上限

如果未调用setRange()指定上限或下�?相应值返回为�?
### datetimepickObject.getRect()

控件区块位置(::RECT结构�?

### datetimepickObject.getRect(true)

控件屏幕区块位置(::RECT结构�?

### datetimepickObject.height

高度

### datetimepickObject.hide

控件是否隐藏

### datetimepickObject.hwnd

控件句柄

### datetimepickObject.id

控件ID

### datetimepickObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/)

使窗口绘图区无效

### datetimepickObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/,0)

使窗口绘图区无效

不刷新背�?
### datetimepickObject.left

左侧坐标

### datetimepickObject.modifyStyle(remove,add,swpFlags)

修改窗口样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### datetimepickObject.modifyStyleEx(remove,add,swpFlags)

修改窗口扩展样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS\_EX_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS\_EX_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### datetimepickObject.onDateTimeChanged

```aardio aardio
datetimepickObject.onDateTimeChanged = function(dateTime,none){
    /*控件变更值回调此函数,
dateTime 为变更后�?time 对象,
none �?则控件值为空，否则为有效时�?/
}

```

### datetimepickObject.onKillFocus

```aardio aardio
datetimepickObject.onKillFocus = function(){
    /*控件失去焦点回调此函�?/
}

```

### datetimepickObject.onSetFocus

```aardio aardio
datetimepickObject.onSetFocus = function(){
    /*控件得到焦点回调此函�?/
}

```

### datetimepickObject.postMessage(msg,wParam,lParam)

投递窗口消息到消息队列�?
此函数用法请参�?::User32.PostMessage

### datetimepickObject.redraw()

刷新

### datetimepickObject.right

右侧坐标

### datetimepickObject.sendMessage(msg,wParam,lParam)

发送窗口消�?
此函数用法请参�?::User32.SendMessage

### datetimepickObject.setFocus()

设置焦点

### datetimepickObject.setFont(指定字体)

指定LOGFONT字体对象,或逻辑字体句柄

### datetimepickObject.setFont(混入字体属�?

```aardio aardio
datetimepickObject.setFont(point=10;name="宋体");

```

### datetimepickObject.setFormat("'时间'hh':'m':'s ddddMMMdd', 'yyy")

所有非格式化字符必须包含在单引号中

### datetimepickObject.setParent(控件对象)

改变父窗�?
### datetimepickObject.setPos(x坐标,y坐标,�?�?插入位置,参数)

调整窗口位置或排�?所有参数可�?
同时指定x,y坐标则移动位�?
同时指定宽高则改变大�?
指定插入位置(句柄或\_HWND前缀常量)则调整Z�?
### datetimepickObject.setRange(时间下限,时间上限)

设置时间范围,参数为time()对象

可省略其中一个参�?仅指定下限或仅指定上�?
### datetimepickObject.setRect(rc)

设置控件区块位置(::RECT结构�?

### datetimepickObject.setRect(rc,true)

设置控件屏幕区块位置(::RECT结构�?

### datetimepickObject.show(true)

显示控件

### datetimepickObject.text

控件文本,也就是格式化以后实际显示的时间字符串

### datetimepickObject.theme

外观主题,例如

winform.button.theme = "Explorer"

winform.button.theme = false

### datetimepickObject.time

获取或设置时�?值为time对象,

在读取此属性值时，保留上次设置此属性的时间对象使用的format字段

[返回对象:timeObject](../../../time/_.html#timeObject)

### datetimepickObject.top

顶部坐标

### datetimepickObject.update()

重绘invalidate函数指定的区�?
### datetimepickObject.width

宽度

### 自动完成常量

\_DTM\_GETMCFONT=0x100A

\_DTM\_GETMONTHCAL=0x1008

\_DTM\_SETMCFONT=0x1009

\_DTN\_CLOSEUP=0xFFFFFD0F

\_DTN\_DATETIMECHANGE=0xFFFFFD09

\_DTN\_DROPDOWN=0xFFFFFD0E

\_DTN\_FIRST2=0xFFFFFD0F

\_DTN\_WMKEYDOWN=0xFFFFFD0B

\_DTS\_SHOWNONE=2

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/win/ui/ctrl/datetimepick.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/win/ui/ctrl/datetimepick.md')

