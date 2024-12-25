[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# win.ui.ctrl.atlax 库模块帮助文�?
## win.ui.ctrl 成员列表

### win.ui.ctrl.atlax

静态文本控件支持库

### win.ui.ctrl.atlax()

静态文本控�?
[返回对象:atlAxWinObject](#atlAxWinObject)

## atlAxWinObject 成员列表

### atlAxWinObject.\_defWindowProc(hwnd,message,wParam,lParam)

用于�?wndproc 回调中提前调用默认消息回调函�?

所有窗口和控件定义�?wndproc 回调以后会自动创建这个函�?

调用此函数以�?wndproc 必须指定�?null 返回�?

以避免再次重复调用默认回调函�?
### atlAxWinObject.\_embedObject

嵌入 COM 控件的容器对�?
[返回对象:embedObject](../../../com/_.html#embedObject)

### atlAxWinObject.\_parentForm

创建该控件的父窗口（win.form对象�?

设计时窗体容器是所有拖放在窗体上的控件�?\_parentForm,

即使窗口移除子窗口样式、更改父子关系，或以 orphanWindow显示,

控件�?\_parentForm 始终都不会改�?
[返回对象:winform](../_.html#winform)

### atlAxWinObject.addCtrl

```aardio aardio
atlAxWinObject.addCtrl(
    button={ cls="button";text="button";left=33;top=32;right=126;bottom=81;autoResize=false }
)

```

### atlAxWinObject.adjust

```aardio aardio
atlAxWinObject.adjust = function( cx,cy,wParam ) {

};

```

### atlAxWinObject.adjust()

调整窗口 \- 自定义事件函�?
### atlAxWinObject.bgcolor

获取或修改景颜色数�?
### atlAxWinObject.bottom

底部坐标

### atlAxWinObject.capture

是否捕获全局鼠标消息

### atlAxWinObject.changeInterval(定时器ID,间隔时间,回调函数)

重新设置间隔时间或回调函�?
### atlAxWinObject.className

运行时类�?
### atlAxWinObject.clearInterval(定时器ID)

删除定时�?
### atlAxWinObject.close()

关闭控件窗口

### atlAxWinObject.cls

设计时类�?
### atlAxWinObject.color

获取或修改字体颜色数�?
### atlAxWinObject.disabled

是否禁用

### atlAxWinObject.getClientRect()

控件客户区块位置(::RECT结构�?

[返回对象:rectObject](../../../global/_.html#rectObject)

### atlAxWinObject.getControl()

返回com控件对象

aardio默认会尝试将atlax创建控件自身注册为默认事件接�?
### atlAxWinObject.getControlClsId()

返回COM对象类名

### atlAxWinObject.getControlTypeName()

返回COM接口�?
### atlAxWinObject.getFont()

控件字体(::LOGFONT结构�?

[返回对象:logfontObject](#logfontObject)

### atlAxWinObject.getForm()

如果是窗体返回自�?
如果是控件则返回\_parentForm

[返回对象:winform](../_.html#winform)

### atlAxWinObject.getParent()

返回父窗�?
[返回对象:atlAxWinObject](#atlAxWinObject)

### atlAxWinObject.getPos()

返回相对坐标,�?�?
x,y,cx,cy=win.getPos(hwnd)

### atlAxWinObject.getRect()

控件区块位置(::RECT结构�?

### atlAxWinObject.getRect(true)

控件屏幕区块位置(::RECT结构�?

### atlAxWinObject.height

高度

### atlAxWinObject.hide

控件是否隐藏

### atlAxWinObject.hwnd

控件句柄

### atlAxWinObject.id

控件ID

### atlAxWinObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/)

使窗口绘图区无效

### atlAxWinObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/,0)

使窗口绘图区无效

不刷新背�?
### atlAxWinObject.isForm

窗体返回true,控件返回false

### atlAxWinObject.left

左侧坐标

### atlAxWinObject.messageOnly()

将窗口转换为message-only window

该窗口不可见,仅用于消息分�?
### atlAxWinObject.modifyStyle(remove,add,swpFlags)

修改窗口样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### atlAxWinObject.modifyStyleEx(remove,add,swpFlags)

修改窗口扩展样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS\_EX_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS\_EX_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### atlAxWinObject.msgbox("字符串参�?)

弹出对话�?可选用参数@2指定标题

### atlAxWinObject.msgboxErr("字符串参�?)

弹出错误对话�?可选用参数@2指定标题

### atlAxWinObject.msgboxTest("字符串参�?)

弹出询问对话�?可选用参数@2指定标题

### atlAxWinObject.orphanWindow(transparent,hwndBuddy,borderless)

创建悬浮窗口�?
悬浮窗口是模仿子窗口外观效果的独立窗口，父窗口可自动调整子窗口到设定位置�?
可选参�?@transparent �?true 则转换为分层透明窗口�?
可选利�?@hwndBuddy 参数指定外部进程窗口句柄的并附加在内部控件上以实现相同的效果�?
伙伴窗口总是会保持在悬浮窗口前面，并保持相同的大小、位置�?
可重复调用此函数更换伙伴窗口，旧的伙伴窗口必须自行关闭�?
可选指�?@borderless 参数 �?true 以移�?@hwndBuddy 的窗口边框�?
### atlAxWinObject.redraw()

刷新

### atlAxWinObject.redrawTransparent()

刷新

透明背景时请使用此函数替代redraw()

### atlAxWinObject.right

右侧坐标

### atlAxWinObject.setFocus()

设置焦点

### atlAxWinObject.setFont(指定字体)

指定LOGFONT字体对象,或逻辑字体句柄

### atlAxWinObject.setFont(混入字体属�?

```aardio aardio
atlAxWinObject.setFont(point=10;name="宋体");

```

### atlAxWinObject.setInterval(回调函数,延时毫秒�?...)

```aardio aardio
atlAxWinObject.setInterval(回调函数,延时毫秒�?...setInterval(
    function(){
        /*参数@1指定执行函数,参数@2指定执行间隔�?可选指定一个或多个回调参数，不指定回调参数则默认为:
 hwnd,message,timerId,tick,

如果在定时器中执行了win.delay等继续消息循环的代码�?在定时器退出前不会再触发同一定时器（重入）�?
定时器回调函数返回数值可修改时间间隔,
返回false取消该定时器*/
    },1000
)

```

### atlAxWinObject.setParent(控件对象)

改变父窗�?
### atlAxWinObject.setPos(x坐标,y坐标,�?�?插入位置,参数)

调整窗口位置或排�?所有参数可�?
同时指定x,y坐标则移动位�?
同时指定宽高则改变大�?
指定插入位置(句柄或\_HWND前缀常量)则调整Z�?
### atlAxWinObject.setRect(rc)

设置控件区块位置(::RECT结构�?

### atlAxWinObject.setRect(rc,true)

设置控件屏幕区块位置(::RECT结构�?

### atlAxWinObject.setRedraw(false)

禁止重绘

### atlAxWinObject.setRedraw(true)

恢复重绘

### atlAxWinObject.show(true)

显示控件

### atlAxWinObject.text

控件文本

### atlAxWinObject.theme

外观主题,例如

winform.button.theme = "Explorer"

winform.button.theme = false

### atlAxWinObject.top

顶部坐标

### atlAxWinObject.translateAccelerator

```aardio aardio
atlAxWinObject.translateAccelerator = function(msg){
    /*返回是否快捷�?/
}

```

### atlAxWinObject.update()

重绘invalidate函数指定的区�?
### atlAxWinObject.width

宽度

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/win/ui/ctrl/atlax.md)

