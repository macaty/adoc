[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# win.ui.tooltip 库模块帮助文�?
命名约定

1、一个提示控件指的是一�?win.ui.tooltip 控件�?原生控件类名 "tooltips\_class32"，在 aardio 里的类名�?"tooltip",
在代码里我们把提示控件我们可以简称为 tooltip 或�?tooltipCtrl�?
这个控件比较特别，没有写�?win.ui.ctrl 名字空间下，也不是由 win.form 创建�?�?win.ui.tooltip 实际上继承了 win.ui.ctrl.metaProperty，仍然由所有者窗口管理�?
提示控件有一点像 aardio 里的 orphanWindow 是一个独立窗口，
所以他没有父窗口而是叫所有者窗口（为便于管理，tooltip 控件 仍然拥有 \_parentForm 属性指向所有者窗口）,

�?tooltip 控件 不会跟随所有者窗口自适应调整显示位置，更不会�?DPI 缩放�?因为这些�?tooltip 控件自己做了�?
2、一个提示控件有一个上层所有者窗口（创建提示控件的时候指定）�?
3、一个「提示控件」可以管理多个「控件提示」，这里有点绕，不要弄反了�?控件提示 —�?也就�?TOOLINFO 结构体，TOOLINFO 类的完整路径�?win.ui.tooltip.TOOLINFO�?
一个控件提示（TOOLINFO）可以关联一个控件窗口，这指的是所有者窗体上的控件窗口�?当然控件提示（TOOLINFO）也可以关联所有者窗体自己�?
一个提示控件里一个窗口对象只能关联一个控件提示（TOOLINFO），
实际上你也不可能关联多个，哪有鼠标晃上去多个提示蹦出来乱跳呢�?
「控件提示」在代码里会称为 toolinfo 或者缩写为 tool�?例如 addTool() 就是添加　TOOLINFO, �?getCurrentTool() 就是获取当前控件提示�?
## win.ui.tooltip 成员列表

提示控件,

提示控件可以有一个所有者窗体，这应当是一�?win.form 对象,

一个提示控件可以管理多个控件提示（ 也就�?TOOLINFO 对象 �?
而每�?TOOLINFO 对象应关联一个所有者窗体上的控件窗�?

当然 TOOLINFO 也可以关闭所有者窗体自�?

同一个提示控件里同一个窗口只能关闭一�?TOOLINFO,

同一控件关联多次会自动覆盖并删除之前创建的关联TOOLINFO

创建提示控件,

提示控件可以有一个所有者窗体，这应当是一�?win.form 对象,

一个提示控件可以管理多个控件提示（ 也就�?TOOLINFO 对象 �?
而每�?TOOLINFO 对象应关联一个所有者窗体上的控件窗�?

当然 TOOLINFO 也可以关闭所有者窗体自�?

同一个提示控件里同一个窗口只能关闭一�?TOOLINFO,

同一控件关联多次会自动覆盖并删除之前创建的关联TOOLINFO

### win.ui.tooltip.balloon

创建汽泡外观提示控件,

一个提示控件有一个所有者窗�?

提示控件可以管理多个控件提示（TOOLINFO�?

每个TOOLINFO关联一个控件窗�?

每个控件窗口同时只能关联一个TOOLINFO

### win.ui.tooltip.balloon()

[返回对象:winUiTooltipObject](#winUiTooltipObject)

### win.ui.tooltip.balloon(所有者窗�?创建参数)

创建汽泡外观提示控件,参数@1为窗体对�?

参数@2使用一个表指定创建选项与样�?可省�?

参数@2的详细用法请参考源码与MSDN文档

### win.ui.tooltip.tracking

创建提示控件,默认使用默认手动跟踪模式,

一个提示控件有一个所有者窗�?

提示控件可以管理多个控件提示（TOOLINFO�?

每个TOOLINFO关联一个控件窗�?

每个控件窗口同时只能关联一个TOOLINFO

### win.ui.tooltip.tracking()

[返回对象:winUiTooltipObject](#winUiTooltipObject)

### win.ui.tooltip.tracking(ownerForm,hasCloseButton,balloon)

创建提示控件,默认使用默认手动跟踪模式,

@ownerForm 参数指定所有者窗口，省略则默认置顶窗口，

@hasCloseButton 参数指定是否显示关闭按钮,可省略默认值为 true

@balloon 参数指定是否启用汽泡外观,可省略默认值为 true

## NMTTCUSTOMDRAWObject 成员列表

### NMTTCUSTOMDRAWObject.drawFlags

提示文本显示格式

此属性会用于 ::DrawText �?uFormat 参数

### NMTTCUSTOMDRAWObject.dwDrawStage

绘图状�?
### NMTTCUSTOMDRAWObject.dwItemSpec

行序�?
### NMTTCUSTOMDRAWObject.hdc

设置句柄

### NMTTCUSTOMDRAWObject.hdr

[返回对象:nmhdrObject](#nmhdrObject)

### NMTTCUSTOMDRAWObject.lItemlParam

自定义数据，LPARAM 参数

### NMTTCUSTOMDRAWObject.rc

[返回对象:rectObject](../../global/_.html#rectObject)

### NMTTCUSTOMDRAWObject.uItemState

状态值，例如 \_CDIS\_FOCUS

### NMTTCUSTOMDRAWObject.update()

更新数据

## win.ui 成员列表

### win.ui.tooltip()

[返回对象:winUiTooltipObject](#winUiTooltipObject)

### win.ui.tooltip(所有者窗�?创建参数)

创建提示控件,

参数@1可选指定所有者窗体对象或所有者窗体句柄，

参数@2使用一个表指定创建选项与样�?可省�?

参数@2的详细用法请参考源码与MSDN文档

### win.ui.tooltip(所有者窗�?提示控件句柄)

绑定现有提示控件,

参数@1可选指定所有者窗体对象或所有者窗体句柄，

参数@2指定现有提示控件句柄

## winUiTooltipInfoObject 成员列表

### winUiTooltipInfoObject.ctrl

创建提示绑定的控件对�?
[返回对象:staticObject](ctrl/static.html#staticObject)

### winUiTooltipInfoObject.delete()

删除提示

### winUiTooltipInfoObject.getText()

返回提示文本

### winUiTooltipInfoObject.sendMessage()

[返回对象:winUiTooltipInfoObject](#winUiTooltipInfoObject)

### winUiTooltipInfoObject.sendMessage(msg,wParam)

发送消息，用法参考此函数源码

此函数返回自�?
### winUiTooltipInfoObject.setText()

[返回对象:winUiTooltipInfoObject](#winUiTooltipInfoObject)

### winUiTooltipInfoObject.setText(text)

设置文本

如果值不�?1或指针则调用 tostring 函数转换为字符串,

@text参数指定要更新的提示文本,

提示必须有文本，否则不会显示,

此函数返回自�?
### winUiTooltipInfoObject.trackPopup

弹出提示

### winUiTooltipInfoObject.trackPopup()

[返回对象:winUiTooltipInfoObject](#winUiTooltipInfoObject)

### winUiTooltipInfoObject.trackPopup(false)

隐藏弹出的提�?
### winUiTooltipInfoObject.trackPopup(text,x,y)

弹出参数 @text 指定文本内容的提�?

可选用x,y参数指定显示坐标,不指定则取最后一次鼠标消息坐�?

此函数返回自�?
### winUiTooltipInfoObject.trackPopup(true,x,y)

弹出提示,

可选用x,y参数指定显示坐标,不指定则取最后一次鼠标消息坐�?

此函数返回自�?
### winUiTooltipInfoObject.updateRect()

修改 rect 字段指定的提示矩形区域后必须调用此函数更�?
可选在参数中指定新�?::RECT 对象,

此函数返回自�?
[返回对象:winUiTooltipInfoObject](#winUiTooltipInfoObject)

## winUiTooltipObject 成员列表

### winUiTooltipObject.activate(false)

停用提示控件,相当于禁用提�?

提示控件在非活动状态时,即使鼠标指针位于绑定的控件窗口上也不会出现提�?
### winUiTooltipObject.activate(true)

激活提示控�?
### winUiTooltipObject.add()

批量添加控件提示

参数应使用一个表指定多个控件的提示文�?

表成员的键为控件�?值为控件提示

### winUiTooltipObject.addTool

创建并返�?TOOLINFO 对象,

提示控件与绑定控件应在同一线程�?
### winUiTooltipObject.addTool()

[返回对象:winUiTooltipInfoObject](#winUiTooltipInfoObject)

### winUiTooltipObject.addTool(ctrl,text,flags)

创建并返回默�?TOOLINFO 对象,

@ctrl参数指定控件对象,省略则设为提示控件所有窗�?
同一窗口在同一提示控件里只能绑定同一个TOOLTIP,

如果窗口之前添加了提示会先删除之前的再添�?

@flags为\_TTF\_前缀常量组合

### winUiTooltipObject.addTrackingTool

创建手动跟踪模式�?TOOLINFO 对象�?
可使�?trackPopup 函数在指定坐标显示，

如果提示控件指定所有窗口并设置标题、启用关闭按钮则可支持超链接

### winUiTooltipObject.addTrackingTool()

[返回对象:winUiTooltipInfoObject](#winUiTooltipInfoObject)

### winUiTooltipObject.addTrackingTool(ctrl,text,flags)

创建手动跟踪模式�?TOOLINFO 对象,

此提示必须使�?trackPopup 函数控制显示或隐�?

可选用@ctrl参数指定一个关联控�?

@ctrl参数指定控件对象,省略则设为提示控件所有窗�?
同一窗口在同一提示控件里只能绑定同一个TOOLTIP,

如果窗口之前添加了提示会先删除之前的再添�?

可选用 @text 参数指定显示文本,支持超链�?

,

提示文本中嵌入超链接格式 [超链接](https://www.aardio.com/),

@flags为可选参�?可用\_TTF\_前缀常量组合

### winUiTooltipObject.adjustRect

对工具提示控件的文本显示矩形与其窗口矩形之间进行自适应转换

### winUiTooltipObject.adjustRect()

[返回对象:rectObject](../../global/_.html#rectObject)

### winUiTooltipObject.adjustRect(rc,false)

参数 @rc 必须是一个指定窗口矩形的 ::RECT 结构

调整该结构体为相应的文本显示矩形,并返回该结构�?
### winUiTooltipObject.adjustRect(rc,true)

参数 @rc 必须是一个指定文本显示的矩形�?::RECT 结构

调整该结构体为相应的窗口矩形,并返回该结构�?
### winUiTooltipObject.capture

是否捕获全局鼠标消息

winex.tooltip 对象如果在调�?trackPopup 后设置此属性为 true�?
则支持点击自动隐藏提�?
### winUiTooltipObject.close()

关闭提示控件

### winUiTooltipObject.delTool(ctrl)

删除提示

参数@1请使用窗口控件对�?

如果控件尚未添加提示则忽略不操作

### winUiTooltipObject.delTool(toolInfo)

删除提示

参数@1请使用addTool函数的返回�?
### winUiTooltipObject.getClientRect()

控件客户区块位置(::RECT结构�?

[返回对象:rectObject](../../global/_.html#rectObject)

### winUiTooltipObject.getCurrentTool()

返回提示控件当前正在使用�?TOOLINFO 对象

[返回对象:winUiTooltipInfoObject](#winUiTooltipInfoObject)

### winUiTooltipObject.getFont()

控件字体(::LOGFONT结构�?

[返回对象:logfontObject](#logfontObject)

### winUiTooltipObject.getNotifyCustomDraw()

[返回对象:NMTTCUSTOMDRAWObject](#NMTTCUSTOMDRAWObject)

### winUiTooltipObject.getNotifyCustomDraw(code,ptr)

NM\_CUSTOMDRAW通知消息返回NMLVCUSTOMDRAW结构�?
### winUiTooltipObject.getParent()

返回父窗�?
[返回对象:winform](_.html#winform)

### winUiTooltipObject.getPos()

返回相对父窗口客户区的坐�?�?�?

参数为true返回屏幕坐标,�?�?

x,y,cx,cy=win.getPos(hwnd)

### winUiTooltipObject.getRect()

控件区块位置(::RECT结构�?

[返回对象:rectObject](../../global/_.html#rectObject)

### winUiTooltipObject.getRect(true)

控件屏幕区块位置(::RECT结构�?

### winUiTooltipObject.getRoot()

获取顶层父窗�?
### winUiTooltipObject.getTool()

[返回对象:winUiTooltipInfoObject](#winUiTooltipInfoObject)

### winUiTooltipObject.getTool(ctrl)

参数指定控件对象

返回该控件关联的TOOLINFO结构�?
不指定参数返回最后一次添加的TOOLINFO结构�?
### winUiTooltipObject.lastToolInfo

最后一次添加的提示结构�?
[返回对象:winUiTooltipInfoObject](#winUiTooltipInfoObject)

### winUiTooltipObject.lastTrackingToolInfo

最后一次添加的手动跟踪模式提示结构�?
[返回对象:winUiTooltipInfoObject](#winUiTooltipInfoObject)

### winUiTooltipObject.modifyStyle(remove,add,swpFlags)

修改窗口样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### winUiTooltipObject.modifyStyleEx(remove,add,swpFlags)

修改窗口扩展样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS\_EX_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS\_EX_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### winUiTooltipObject.onDestroy

```aardio aardio
winUiTooltipObject.onDestroy = function(){
    /*窗口销毁前触发*/
}

```

### winUiTooltipObject.onHyperlinkClick(href,title)

```aardio aardio
winUiTooltipObject.onHyperlinkClick = function(href,title){
    /*点击了超链接,
@href 为链接地址,@title 参数为超链接包含文本,
提示文本中嵌入超链接格式<a href="https://www.aardio.com">超链�?/a>
一个提示里只能写一个超链接,不要写多�?/
}

```

### winUiTooltipObject.onPopupHide()

```aardio aardio
winUiTooltipObject.onPopupHide = function(){
    /*隐藏提示触发此通知�?
父窗口不�?win.form 对象则此事件不可用，
替代方法是在此控件的 wndproc 回调中处�?_WM_SHOWWINDOW 消息*/
}

```

### winUiTooltipObject.onPopupShow()

```aardio aardio
winUiTooltipObject.onPopupShow = function(){
    /*显示提示触发此通知�?
父窗口不�?win.form 对象则此事件不可用，
替代方法是在此控件的 wndproc 回调中处�?_WM_SHOWWINDOW 消息*/
}

```

### winUiTooltipObject.onnotify

```aardio aardio
winUiTooltipObject.onnotify = function(id,code,ptr){
    /*通知事件触发*/
}

```

### winUiTooltipObject.popup(false)

隐藏提示

不触发onPopupHide

### winUiTooltipObject.postMessage(msg,wParam,lParam)

投递窗口消息到消息队列�?
此函数用法请参�?::User32.PostMessage

### winUiTooltipObject.ptInClientRect

判断指定的坐标是否在客户区内

### winUiTooltipObject.ptInClientRect(lParam)

使用窗口消息回调函数�?lParam 参数获取 x,y 坐标�?
如果 x,y 坐标在客户区内返�?true

### winUiTooltipObject.ptInClientRect(x,y)

x,y 坐标是否在客户区�?
### winUiTooltipObject.redraw()

刷新

### winUiTooltipObject.sendMessage(msg,wParam,lParam)

发送窗口消�?
此函数用法请参�?::User32.SendMessage

### winUiTooltipObject.setBkColor(颜色�?

设置背景颜色

### winUiTooltipObject.setDelayTime(超时�?选项)

光标在控件上悬停并超出一定时间才会显�?

默认值约为半秒，此函数可修改默认的超时�?
以毫秒为单位,

选项为可选参�?默认�?0/\*\_TTDT\_AUTOMATIC\*/

### winUiTooltipObject.setError()

[返回对象:winUiTooltipObject](#winUiTooltipObject)

### winUiTooltipObject.setError(title,large)

设置@title参数指定的标�?并显示错误图�?

可选用@large指定是否使用大图�?
### winUiTooltipObject.setFont(指定字体)

指定LOGFONT字体对象,或逻辑字体句柄

### winUiTooltipObject.setFont(混入字体属�?

```aardio aardio
winUiTooltipObject.setFont(point=10;name="宋体");

```

### winUiTooltipObject.setInfo()

[返回对象:winUiTooltipObject](#winUiTooltipObject)

### winUiTooltipObject.setInfo(title,large)

设置@title参数指定的标�?并显示信息图�?

可选用@large指定是否使用大图�?
### winUiTooltipObject.setMaxWidth(宽度)

设置提示框最大宽�?
### winUiTooltipObject.setPos(x坐标,y坐标,�?�?插入位置,参数)

调整窗口位置或排�?所有参数可�?
同时指定x,y坐标则移动位�?
同时指定宽高则改变大�?
指定插入位置(句柄或\_HWND前缀常量)则调整Z�?
### winUiTooltipObject.setRect(rc)

设置控件区块位置(::RECT结构�?

### winUiTooltipObject.setRect(rc,true)

设置控件屏幕区块位置(::RECT结构�?

### winUiTooltipObject.setText()

[返回对象:winUiTooltipInfoObject](#winUiTooltipInfoObject)

### winUiTooltipObject.setText(text,ctrlOrToolInfo)

更新提示文本,

提示必须有文本，否则不会显示,

addTrackingTool 函数创建的提示支持超链接,

提示文本中嵌入超链接格式 [超链接](https://www.aardio.com/),

可选用参数@ctrlOrToolInfo指定控件或TOOLINFO结构�?

如果不指定则默认使用最后一次添加的TOOLINFO结构�?

成功返回TOOLINFO结构�?
### winUiTooltipObject.setTextColor(颜色�?

设置文本颜色

### winUiTooltipObject.setTitle()

[返回对象:winUiTooltipObject](#winUiTooltipObject)

### winUiTooltipObject.setTitle(title,icon)

设置@title参数指定的标�?

可选用@icon参数指定图标句柄,

工具有标题才会显示图�?

只设置标题不设置文本则不会显�?
### winUiTooltipObject.setWarning()

[返回对象:winUiTooltipObject](#winUiTooltipObject)

### winUiTooltipObject.setWarning(title,large)

设置@title参数指定的标�?并显示警告图�?

可选用@large指定是否使用大图�?
### winUiTooltipObject.show(true)

显示控件

### winUiTooltipObject.text

当前显示文本,

包含提示标题与内�?

此属性只�?

### winUiTooltipObject.trackPopup

此函数调用最后一次创建的手动跟踪模式 TOOLINFO 对象�?
这指的是在调用此函数以前执行过以下操作（其中之一）：

1、调�?addTrackingTool 函数

2、win.ui.tooltip.tracking 创建的提示控件调用以默认 flags 创建提示的部分函�?
这包�?addTool, setText 等函�?
注意调用此函数显示的提示提示默认不会自动隐藏�?
winex.tooltip 在调用此函数后设�?capture �?true 支持点击隐藏

### winUiTooltipObject.trackPopup()

[返回对象:winUiTooltipInfoObject](#winUiTooltipInfoObject)

### winUiTooltipObject.trackPopup(false)

隐藏弹出的提�?
### winUiTooltipObject.trackPopup(text,x,y)

弹出参数 @text 指定文本内容的提�?

可选用x,y参数指定显示坐标,不指定则取最后一次鼠标消息坐标�?
此函数返回显示的 TOOLINFO 对象

### winUiTooltipObject.trackPopup(true,x,y)

弹出提示,

可选用x,y参数指定显示坐标,不指定则取最后一次鼠标消息坐标�?
此函数返回显示的 TOOLINFO 对象

### winUiTooltipObject.trackPos()

[返回对象:winUiTooltipInfoObject](#winUiTooltipInfoObject)

### winUiTooltipObject.trackPos(x,y)

移动到指定坐�?

省略参数是移动到最后一次处理鼠标消息的坐标,

请使用trackPopup函数控制显示和隐�?
此函数返回自�?
### winUiTooltipObject.update()

刷新

### winUiTooltipObject.wait(等待函数,超时,延时间隔)

循环执行等待函数,并等待返回�?
直到等待函数返回非空�?或存在第二个返回�?或当前窗口关�?
等待函数返回的值就是wait函数的返回�?

如果指定超时,超过指定毫秒时返回null,

除等待函数以�?所有参数可�?
### winUiTooltipObject.wndproc

```aardio aardio
winUiTooltipObject.wndproc = function(hwnd,message,wParam,lParam){
    /*窗口消息回调，返回任意非null值阻止默认回�?wndproc重复赋值时追加函数而不是覆盖之前的回调
设为null添除所有消息回调函�?wndproc也可以是一个表,键要为处理的消息,值为对应的消息回调函�?/
}

```

### 自动完成常量

\_TTF\_ABSOLUTE=0x80

\_TTF\_CENTERTIP=2

\_TTF\_DI\_SETITEM=0x8000

\_TTF\_IDISHWND=1

\_TTF\_PARSELINKS=0x1000

\_TTF\_RTLREADING=4

\_TTF\_TRACK=0x20

\_TTF\_TRANSPARENT=0x100

\_TTN\_FIRST=0xFFFFFDF8

\_TTN\_GETDISPINFO=0xFFFFFDF8

\_TTN\_LAST=0xFFFFFFCA

\_TTN\_LINKCLICK=0xFFFFFDF5

\_TTN\_NEEDTEXT=0xFFFFFDF8

\_TTN\_POP=0xFFFFFDF6

\_TTN\_SHOW=0xFFFFFDF7

\_TTS\_ALWAYSTIP=1

\_TTS\_BALLOON=0x40

\_TTS\_CLOSE=0x80

\_TTS\_NOANIMATE=0x10

\_TTS\_NOFADE=0x20

\_TTS\_NOPREFIX=2

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/win/ui/tooltip.md)

