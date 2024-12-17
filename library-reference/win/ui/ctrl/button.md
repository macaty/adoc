[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# win.ui.ctrl.button 库模块帮助文�?
## win.ui.ctrl 成员列表

### win.ui.ctrl.button()

控钮控件

checkbox.radiobutton 等控件继承自 button 控件,

button 控件默认会忽略背景色、字体颜色属�?

在创建参数中指定 note 属性时会切换为「命令链接」样�?
[返回对象:buttonObject](#buttonObject)

### win.ui.ctrl.checkbox()

复选控钮控�?
[返回对象:checkboxObject](#checkboxObject)

### win.ui.ctrl.groupbox()

控钮控件

[返回对象:staticObject](static.html#staticObject)

### win.ui.ctrl.radiobutton()

单选控钮控�?
[返回对象:radiobuttonObject](#radiobuttonObject)

## buttonObject 成员列表

### buttonObject.\_defWindowProc(hwnd,message,wParam,lParam)

用于�?wndproc 回调中提前调用默认消息回调函�?

所有窗口和控件定义�?wndproc 回调以后会自动创建这个函�?

调用此函数以�?wndproc 必须指定�?null 返回�?

以避免再次重复调用默认回调函�?
### buttonObject.\_parentForm

创建该控件的父窗口（win.form对象�?

设计时窗体容器是所有拖放在窗体上的控件�?\_parentForm,

即使窗口移除子窗口样式、更改父子关系，或以 orphanWindow显示,

控件�?\_parentForm 始终都不会改�?
[返回对象:winform](../_.html#winform)

### buttonObject.bottom

底部坐标

### buttonObject.capture

是否捕获全局鼠标消息

### buttonObject.className

运行时类�?
### buttonObject.close()

关闭控件窗口

### buttonObject.cls

设计时类�?
### buttonObject.disabled

是否禁用

### buttonObject.disabledText

```aardio aardio
buttonObject.disabledText = {"�?;"�?;"�?;"�?;"�?;"�?}/*disabledText 属性指定为文本时，禁用此控件并显示指定文本�?指定为数组时,创建动画并在原控件文本前面循环显示数组中的字符串�?数组内可选用 text 属性指定按钮禁用状态按钮主文本�?disabledText 属性指定为 null 时，启用此控件并恢复控件之前的正常文本�?/

```

### buttonObject.dpiScaleX

窗口当前使用的DPI横坐标缩放系�?

该值由界面系统自动维护，任何情况下都不应手动修�?

这是一个以小数表示百分比的数，例如 1.25 表示 125%,

窗口未使用缩放或未完成缩放初始化时，值可能为 null�?
如果要获取屏幕缩放设置应改用 gdi.getDpiScale 函数

### buttonObject.dpiScaleY

窗口当前使用的DPI纵坐标缩放系�?

该值由界面系统自动维护，任何情况下都不应手动修�?

这是一个以小数表示百分比的数，例如 1.25 表示 125%,

窗口未使用缩放或未完成缩放初始化时，值可能为 null�?
如果要获取屏幕缩放设置应改用 gdi.getDpiScale 函数

### buttonObject.font

控件字体（LOGFONT 结构体）�?
注意获取该属性总是返回新的 LOGFONT 对象�?
修改返回字体并不会更新控件字体，

除非重新赋值�?
建议尽量优先使用 getFont �?setFont 函数�?
以增强代码可读�?
字体会根据控件设置自动处�?DPI 缩放，不需要事先缩放字体大�?
### buttonObject.getClientRect()

控件客户区块位置(::RECT结构�?

[返回对象:rectObject](../../../global/_.html#rectObject)

### buttonObject.getFont()

返回控件 LOGFONT 字体�?
返回对象�?h 值会按控件的 DPI 缩放设置自动还原为缩放前大小�?
[返回对象:logfontObject](#logfontObject)

### buttonObject.getFont(true)

返回控件 LOGFONT 字体�?
返回对象�?h 值为字体实际大小，不会按控件 DPI 设置还原�?
返回字体会设�?noScale 属性为 true,

使用控件�?setFont 函数或赋�?font 属性时�?
noScale 属性为 true 的字体同样不会进行自�?DPI 缩放

[返回对象:logfontObject](#logfontObject)

### buttonObject.getParent()

返回父窗�?
[返回对象:staticObject](static.html#staticObject)

### buttonObject.getPos()

返回相对坐标,�?�?
x,y,cx,cy=win.getPos(hwnd)

### buttonObject.getRect()

控件区块位置(::RECT结构�?

### buttonObject.getRect(true)

控件屏幕区块位置(::RECT结构�?

### buttonObject.height

高度

### buttonObject.hide

当前控件窗口是否隐藏�?
仅检查当前窗口的可见性样式（窗口 是否移除�?\_WS\_VISIBLE 样式）�?
不考虑父窗口是否可见，不考虑是否被其他窗口遮挡�?
如果需要同时判断父窗口的可见性，应改�?win.isVisible 函数�?
### buttonObject.hwnd

控件句柄

### buttonObject.id

控件ID

### buttonObject.image

按钮图片或图�?
赋值必须是图片文件路径或数�?
位图句柄由窗体负责销�?
取值时返回位图句柄

### buttonObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/)

使窗口绘图区无效

### buttonObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/,0)

使窗口绘图区无效

不刷新背�?
### buttonObject.left

左侧坐标

### buttonObject.modifyStyle(remove,add,swpFlags)

修改窗口样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### buttonObject.modifyStyleEx(remove,add,swpFlags)

修改窗口扩展样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS\_EX_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS\_EX_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### buttonObject.note

设置按钮附注

必须在创建控件的初始化参数中也指定该属�?

指定该属性会切换为「命令链接」样�?

支持Vista,Win7 以及之后的系�?不支�?XP 系统

「命令链接」样式忽略控件的字体设置，但支持背景色属�?
### buttonObject.onDrawItem(drawItem,dpiScaleX,dpiScaleY)

```aardio aardio
buttonObject.onDrawItem = function(drawItem){
    /*控件属性里指定 ownerDraw �?true 触发此事�?在这里自绘控件项*/
}

```

### buttonObject.onMeasureItem(measureItem,dpiScaleX,dpiScaleY)

```aardio aardio
buttonObject.onMeasureItem = function(measureItem){
    measureItem.itemHeight = 51;
    /*控件属性里指定 ownerDraw �?true 触发此事�?在这里配置自绘控件项参数*/
}

```

### buttonObject.orphanWindow(transparent,hwndBuddy,borderless)

创建悬浮窗口�?
悬浮窗口是模仿子窗口外观效果的独立窗口，父窗口可自动调整子窗口到设定位置�?
可选参�?@transparent �?true 则转换为分层透明窗口�?
可选利�?@hwndBuddy 参数指定外部进程窗口句柄的并附加在内部控件上以实现相同的效果�?
伙伴窗口总是会保持在悬浮窗口前面，并保持相同的大小、位置�?
可重复调用此函数更换伙伴窗口，旧的伙伴窗口必须自行关闭�?
可选指�?@borderless 参数 �?true 以移�?@hwndBuddy 的窗口边框�?
### buttonObject.postMessage(msg,wParam,lParam)

投递窗口消息到消息队列�?
此函数用法请参�?::User32.PostMessage

### buttonObject.publish("字符串参�?,)

在窗口所在界面线程发布消�?

运行界面线程所有所有调用subscribe函数订阅此消息的函数,

可添加任意个触发参数

### buttonObject.redraw()

刷新

### buttonObject.reloadScale()

按设计时位置参数、重新调整控件位置以适应窗口当前缩放比例�?
父窗口缩放时会自动执行此操作�?
默认在启动窗口消息循环时会自适应调整所有控件�?
所以在启动消息循环前添加控件不必调用此函数�?
### buttonObject.right

右侧坐标

### buttonObject.saveScale()

根据控件当前位置、缩放比例，更新控件的设计时位置参数�?
以避免下次窗口缩放自适应调整控件当前位置更改被清除，

控件所有调整位置的属性或成员函数已自动调用此函数�?
### buttonObject.sendMessage(msg,wParam,lParam)

发送窗口消�?
此函数用法请参�?::User32.SendMessage

### buttonObject.setFocus()

设置焦点

### buttonObject.setFont(指定字体)

指定 LOGFONT 字体对象,或逻辑字体句柄

如果不指�?point 值并指定 h 值，字体会按控件�?DPI 缩放设置自动缩放�?
### buttonObject.setFont(混入字体属�?

```aardio aardio
buttonObject.setFont(h=-12;name="Tahoma");

```

### buttonObject.setIcon(图标句柄)

设置图标

成功返回true,自动销毁原来的位图

### buttonObject.setIcon(图标句柄,false)

设置图标

成功返回控件原来的位图句�?

必须调用::DeleteObject()函数销毁该句柄

### buttonObject.setImage(图片句柄)

设置图片

成功返回true,自动销毁原来的位图

### buttonObject.setImage(图片句柄,false)

设置图片

成功返回控件原来的位图句�?

必须调用::DeleteObject()函数销毁该句柄

### buttonObject.setParent(控件对象)

改变父窗�?
### buttonObject.setPos(x坐标,y坐标,�?�?插入位置,参数)

调整窗口位置或排�?所有参数可�?
同时指定x,y坐标则移动位�?
同时指定宽高则改变大�?
指定插入位置(句柄或\_HWND前缀常量)则调整Z�?
### buttonObject.setRect(rc)

设置控件区块位置(::RECT结构�?

### buttonObject.setRect(rc,true)

设置控件屏幕区块位置(::RECT结构�?

### buttonObject.show(true)

显示控件

### buttonObject.text

按钮文本属�?
### buttonObject.theme

外观主题,例如

winform.button.theme = "Explorer"

winform.button.theme = false

### buttonObject.threadCallable()

开启此控件的跨线程调用功能

### buttonObject.top

顶部坐标

### buttonObject.translateCommand()

允许转发转发子窗口的命令（\_WM\_COMMAND）与通知（\_WM\_NOTIFY）消息，

避免子窗�?oncommand，onnotify 等回调失效�?
同时会处理子窗口�?\_WM\_CTLCOLORSTATIC 等消息，

以避免部分外观属性失�?
### buttonObject.update()

重绘invalidate函数指定的区�?
### buttonObject.valid

窗口是否有效�?
窗口未关闭返�?true �?
窗口已关闭或正在关闭返回 false

### buttonObject.width

宽度

## checkboxObject 成员列表

### checkboxObject.\_defWindowProc(hwnd,message,wParam,lParam)

用于�?wndproc 回调中提前调用默认消息回调函�?

所有窗口和控件定义�?wndproc 回调以后会自动创建这个函�?

调用此函数以�?wndproc 必须指定�?null 返回�?

以避免再次重复调用默认回调函�?
### checkboxObject.\_parentForm

创建该控件的父窗口（win.form对象�?

设计时窗体容器是所有拖放在窗体上的控件�?\_parentForm,

即使窗口移除子窗口样式、更改父子关系，或以 orphanWindow显示,

控件�?\_parentForm 始终都不会改�?
[返回对象:winform](../_.html#winform)

### checkboxObject.bottom

底部坐标

### checkboxObject.capture

是否捕获全局鼠标消息

### checkboxObject.checked

复选框是否选中状�?
### checkboxObject.close()

关闭控件窗口

### checkboxObject.disabled

是否禁用

### checkboxObject.getClientRect()

控件客户区块位置(::RECT结构�?

[返回对象:rectObject](../../../global/_.html#rectObject)

### checkboxObject.getFont()

控件字体(::LOGFONT结构�?

!logfont

[返回对象:logfontObject](#logfontObject)

### checkboxObject.getParent()

返回父窗�?
[返回对象:staticObject](static.html#staticObject)

### checkboxObject.getPos()

返回相对坐标,�?�?
x,y,cx,cy=win.getPos(hwnd)

### checkboxObject.getRect()

控件区块位置(::RECT结构�?

### checkboxObject.getRect(true)

控件屏幕区块位置(::RECT结构�?

### checkboxObject.height

高度

### checkboxObject.hide

控件是否隐藏

### checkboxObject.hwnd

控件句柄

### checkboxObject.id

控件ID

### checkboxObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/)

使窗口绘图区无效

### checkboxObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/,0)

使窗口绘图区无效

不刷新背�?
### checkboxObject.left

左侧坐标

### checkboxObject.modifyStyle(remove,add,swpFlags)

修改窗口样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### checkboxObject.modifyStyleEx(remove,add,swpFlags)

修改窗口扩展样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS\_EX_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS\_EX_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### checkboxObject.onDrawItem(drawItem)

```aardio aardio
checkboxObject.onDrawItem = function(drawItem){

}

```

### checkboxObject.onMeasureItem(measureItem)

```aardio aardio
checkboxObject.onMeasureItem = function(measureItem){
    measureItem.itemHeight = 51;
}

```

### checkboxObject.postMessage(msg,wParam,lParam)

投递窗口消息到消息队列�?
此函数用法请参�?::User32.PostMessage

### checkboxObject.redraw()

刷新

### checkboxObject.right

右侧坐标

### checkboxObject.sendMessage(msg,wParam,lParam)

发送窗口消�?
此函数用法请参�?::User32.SendMessage

### checkboxObject.setFocus()

设置焦点

### checkboxObject.setFont(指定字体)

指定LOGFONT字体对象,或逻辑字体句柄

### checkboxObject.setFont(混入字体属�?

```aardio aardio
checkboxObject.setFont(point=10;name="宋体");

```

### checkboxObject.setParent(控件对象)

改变父窗�?
### checkboxObject.setPos(x坐标,y坐标,�?�?插入位置,参数)

调整窗口位置或排�?所有参数可�?
同时指定x,y坐标则移动位�?
同时指定宽高则改变大�?
指定插入位置(句柄或\_HWND前缀常量)则调整Z�?
### checkboxObject.setRect(rc)

设置控件区块位置(::RECT结构�?

### checkboxObject.setRect(rc,true)

设置控件屏幕区块位置(::RECT结构�?

### checkboxObject.show(true)

显示控件

### checkboxObject.theme

外观主题,例如

winform.button.theme = "Explorer"

winform.button.theme = false

### checkboxObject.threadCallable()

开启此控件的跨线程调用功能

### checkboxObject.top

顶部坐标

### checkboxObject.update()

重绘invalidate函数指定的区�?
### checkboxObject.width

宽度

## radiobuttonObject 成员列表

### radiobuttonObject.\_defWindowProc(hwnd,message,wParam,lParam)

用于�?wndproc 回调中提前调用默认消息回调函�?

所有窗口和控件定义�?wndproc 回调以后会自动创建这个函�?

调用此函数以�?wndproc 必须指定�?null 返回�?

以避免再次重复调用默认回调函�?
### radiobuttonObject.\_parentForm

创建该控件的父窗口（win.form对象�?

设计时窗体容器是所有拖放在窗体上的控件�?\_parentForm,

即使窗口移除子窗口样式、更改父子关系，或以 orphanWindow显示,

控件�?\_parentForm 始终都不会改�?
[返回对象:winform](../_.html#winform)

### radiobuttonObject.bottom

底部坐标

### radiobuttonObject.capture

是否捕获全局鼠标消息

### radiobuttonObject.checked

单选按钮否选中状�?
### radiobuttonObject.close()

关闭控件�?
### radiobuttonObject.disabled

是否禁用

### radiobuttonObject.getClientRect()

控件客户区块位置(::RECT结构�?

[返回对象:rectObject](../../../global/_.html#rectObject)

### radiobuttonObject.getFont()

控件字体(::LOGFONT结构�?

!logfont

[返回对象:logfontObject](#logfontObject)

### radiobuttonObject.getParent()

返回父窗�?
[返回对象:staticObject](static.html#staticObject)

### radiobuttonObject.getPos()

返回相对坐标,�?�?
x,y,cx,cy=win.getPos(hwnd)

### radiobuttonObject.getRect()

控件区块位置(::RECT结构�?

### radiobuttonObject.getRect(true)

控件屏幕区块位置(::RECT结构�?

### radiobuttonObject.height

高度

### radiobuttonObject.hide

控件是否隐藏

### radiobuttonObject.hwnd

控件句柄

### radiobuttonObject.id

控件ID

### radiobuttonObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/)

使窗口绘图区无效

### radiobuttonObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/,0)

使窗口绘图区无效

不刷新背�?
### radiobuttonObject.left

左侧坐标

### radiobuttonObject.modifyStyle(remove,add,swpFlags)

修改窗口样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### radiobuttonObject.modifyStyleEx(remove,add,swpFlags)

修改窗口扩展样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS\_EX_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS\_EX_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### radiobuttonObject.onDrawItem(drawItem)

```aardio aardio
radiobuttonObject.onDrawItem = function(drawItem){

}

```

### radiobuttonObject.onMeasureItem(measureItem)

```aardio aardio
radiobuttonObject.onMeasureItem = function(measureItem){
    measureItem.itemHeight = 51;
}

```

### radiobuttonObject.postMessage(msg,wParam,lParam)

投递窗口消息到消息队列�?
此函数用法请参�?::User32.PostMessage

### radiobuttonObject.redraw()

刷新

### radiobuttonObject.right

右侧坐标

### radiobuttonObject.sendMessage(msg,wParam,lParam)

发送窗口消�?
此函数用法请参�?::User32.SendMessage

### radiobuttonObject.setFocus()

设置焦点

### radiobuttonObject.setFont(指定字体)

指定LOGFONT字体对象,或逻辑字体句柄

### radiobuttonObject.setFont(混入字体属�?

```aardio aardio
radiobuttonObject.setFont(point=10;name="宋体");

```

### radiobuttonObject.setParent(控件对象)

改变父窗�?
### radiobuttonObject.setPos(x坐标,y坐标,�?�?插入位置,参数)

调整窗口位置或排�?所有参数可�?
同时指定x,y坐标则移动位�?
同时指定宽高则改变大�?
指定插入位置(句柄或\_HWND前缀常量)则调整Z�?
### radiobuttonObject.setRect(rc)

设置控件区块位置(::RECT结构�?

### radiobuttonObject.setRect(rc,true)

设置控件屏幕区块位置(::RECT结构�?

### radiobuttonObject.show(true)

显示控件

### radiobuttonObject.theme

外观主题,例如

winform.button.theme = "Explorer"

winform.button.theme = false

### radiobuttonObject.threadCallable()

开启此控件的跨线程调用功能

### radiobuttonObject.top

顶部坐标

### radiobuttonObject.update()

重绘invalidate函数指定的区�?
### radiobuttonObject.width

宽度

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/win/ui/ctrl/button.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/win/ui/ctrl/button.md')

