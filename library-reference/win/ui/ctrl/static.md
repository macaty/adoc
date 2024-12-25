[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# win.ui.ctrl.static 库模块帮助文�?
## win.ui.ctrl 成员列表

### win.ui.ctrl.static

静态文本控件支持库

### win.ui.ctrl.static()

静态文本控�?
[返回对象:staticObject](static.html#staticObject)

## staticObject 成员列表

### staticObject.\_defWindowProc(hwnd,message,wParam,lParam)

用于�?wndproc 回调中提前调用默认消息回调函�?

所有窗口和控件定义�?wndproc 回调以后会自动创建这个函�?

调用此函数以�?wndproc 必须指定�?null 返回�?

以避免再次重复调用默认回调函�?
### staticObject.\_embedObject

嵌入 COM 控件的容器对�?
[返回对象:embedObject](../../../com/_.html#embedObject)

### staticObject.\_parentForm

创建该控件的父窗口（win.form对象�?

设计时窗体容器是所有拖放在窗体上的控件�?\_parentForm,

即使窗口移除子窗口样式、更改父子关系，或以 orphanWindow显示,

控件�?\_parentForm 始终都不会改�?
[返回对象:winform](../_.html#winform)

### staticObject.addCtrl

```aardio aardio
staticObject.addCtrl(
    button={ cls="button";text="button";left=33;top=32;right=126;bottom=81;autoResize=false }
)

```

### staticObject.adjust

```aardio aardio
staticObject.adjust = function( cx,cy,wParam ) {
    /*窗口缩放后会自动触发此函数�?cx 参数为窗口宽�?cy 参数为窗口高�?
wParam 参数请参�?_WM_SIZE 消息参数说明,一般不用管�?
所�?win.form 创建的窗体和控件都支持此事件,
重复赋值只会追加而不会覆盖此事件�?一般不建议添加一�?wndproc 仅仅是为了处�? _WM_SIZE 消息�?定义 adjust 事件是更好的选择�?
可主动调用此事件,省略参数�?cx,cy 参数默认设为窗口大小*/
};

```

### staticObject.autoResize

是否允许跟随父窗体自动缩�?
### staticObject.bgcolor

获取或修改景颜色数�?
### staticObject.bottom

底部坐标

### staticObject.capture

是否捕获全局鼠标消息

### staticObject.changeInterval(定时器ID,间隔时间,回调函数)

重新设置间隔时间或回调函�?
### staticObject.className

运行时类�?
### staticObject.clearInterval(定时器ID)

删除定时器�?
参数如果�?null 则忽略不执行�?
否则定时器ID必须�?setInterval 函数或setTimeout函数的返回值�?
请注意如果定时器被删除，ID 可能被重新分配给其他定时器�?
在定时器回调函数中返�?0,false 以删除定时器是更稳妥的方�?
### staticObject.clearTimeout(定时器ID)

删除定时器�?
参数如果�?null 则忽略不执行�?
否则定时器ID必须�?setInterval 函数或setTimeout�?数的返回值�?
请注意如果定时器被删除，ID 可能被重新分配给其他定时器�?
在定时器回调函数中返�?0,false 以删除定时器是更稳妥的方�?
### staticObject.close()

关闭控件窗口

### staticObject.cls

设计时类�?
### staticObject.color

获取或修改字体颜色数�?
### staticObject.createEmbed

创建嵌入控件,返回控件容器对象,

容器对象�?\_object 成员是创建的 COM 对象,

容器对象可通过添加成员函数响应 COM 对象事件�?
容器对象的主要作用是充当访问 COM 对象的中间代理对象�?
通常使用 util.metaProperty 为容器对象添加属性元表，

属性元表可拦截属性、函数调用并调用 \_object 对象,

createEmbedEx 返回的容器已添加默认代理以直接访�?COM 对象

### staticObject.createEmbed()

[返回对象:embedObject](../../../com/_.html#embedObject)

### staticObject.createEmbed(clsId,embedObj)

创建嵌入控件,返回控件容器对象,

容器对象�?\_object 成员是创建的 COM 对象,

容器对象可通过添加成员函数响应 COM 对象事件�?
容器对象的主要作用是充当访问 COM 对象的中间代理对�?

@clsId 指定控件 CLSID,

可选在参数@2中指�?COM 对象绑定的容器对�?
此函数失败会抛出异常

### staticObject.createEmbed(comObject,embedObj)

嵌入 COM 控件,返回控件容器对象,

容器对象�?\_object 成员是传入的 COM 对象,

容器对象可通过添加成员函数响应 COM 对象事件�?
容器对象的主要作用是充当访问 COM 对象的中间代理对�?

@comObject 指定已创建成功的 COM 对象,

可选在参数@2中指�?COM 对象绑定的容器对�?
此函数失败会抛出异常

### staticObject.createEmbedEx

创建嵌入 COM 控件，返回控件容器对象�?
容器对象�?_object 成员是创建的 COM 对象。_

_容器对象�?\_\_event_\_ 成员�?COM 对象默认事件监听器�?
在窗口销毁时解除默认事件监听器并释放 COM 对象�?
返回容器已添加元表，可通过容器对象的成员代理访�?COM 对象成员�?
也可以通过指定容器对象的成员函数响�?COM 对象事件

### staticObject.createEmbedEx()

[返回对象:embedObject](../../../com/_.html#embedObject)

### staticObject.createEmbedEx(clsId,embedObj)

创建嵌入 COM 控件，返回控件容器对象�?
此函数返回的容器已添加元表并创建代理以直接访�?COM 对象�?
也可以通过指定容器对象的成员函数响�?COM 对象事件�?
@clsId 指定控件 CLSID�?
可选在参数 @2 中指�?COM 对象绑定的容器对象�?
此函数失败会抛出异常

### staticObject.createEmbedEx(comObject,embedObj)

嵌入 COM 控件，返回控件容器对象�?
此函数返回的容器已添加元表并创建代理以直接访�?COM对象�?
也可以通过指定容器对象的成员函数响�?COM 对象事件�?
参数 @comObject 指定已创建成功的 COM 对象,

可选在参数 @2 中指�?COM 对象绑定的容器对象�?
此函数失败会抛出异常

### staticObject.disabled

是否禁用

### staticObject.disabledText

指定文本�?禁用此控�?并显示指定文�?

指定为null�?启用此控�?并恢复控件之前的正常文本

### staticObject.dpiScale(x,y)

�?@x,@y 表示的像素值乘以窗体当�?DPI 缩放倍数并返�?

省略 @y 参数时仅返回 @x 转换后的�?

所�?win.ui 创建的窗口或控件都提供这个函�?
### staticObject.dpiScaleX

窗口当前使用的DPI横坐标缩放系�?

该值由界面系统自动维护，任何情况下都不应手动修�?

这是一个以小数表示百分比的数，例如 1.25 表示 125%,

窗口未使用缩放或未完成缩放初始化时，值可能为 null�?
如果要获取屏幕缩放设置应改用 gdi.getDpiScale 函数

### staticObject.dpiScaleY

窗口当前使用的DPI纵坐标缩放系�?

该值由界面系统自动维护，任何情况下都不应手动修�?

这是一个以小数表示百分比的数，例如 1.25 表示 125%,

窗口未使用缩放或未完成缩放初始化时，值可能为 null�?
如果要获取屏幕缩放设置应改用 gdi.getDpiScale 函数

### staticObject.ellipsis

超出显示范围如何显示省略号，可选值：

"path" 单行显示，在最后一个反斜杆前显示省略号

"end" 单行显示，字符串末尾超出显示范围则显示省略号

null 不显示省略号

### staticObject.enableDpiScaling(false)

禁用DPI自动缩放,

不指定参数启用DPI自动缩放,默认已启�?
### staticObject.font

控件字体（LOGFONT 结构体）�?
注意获取该属性总是返回新的 LOGFONT 对象�?
修改返回字体并不会更新控件字体，

除非重新赋值�?
建议尽量优先使用 getFont �?setFont 函数�?
以增强代码可读�?
字体会根据控件设置自动处�?DPI 缩放，不需要事先缩放字体大�?
### staticObject.getClientRect()

控件客户区块位置(::RECT结构�?

[返回对象:rectObject](../../../global/_.html#rectObject)

### staticObject.getFont()

返回控件 LOGFONT 字体�?
返回对象�?h 值会按控件的 DPI 缩放设置自动还原为缩放前大小�?
[返回对象:logfontObject](#logfontObject)

### staticObject.getFont(true)

返回控件 LOGFONT 字体�?
返回对象�?h 值为字体实际大小，不会按控件 DPI 设置还原�?
返回字体会设�?noScale 属性为 true,

使用控件�?setFont 函数或赋�?font 属性时�?
noScale 属性为 true 的字体同样不会进行自�?DPI 缩放

[返回对象:logfontObject](#logfontObject)

### staticObject.getForm()

如果是窗体返回自�?
如果是控件则返回\_parentForm

[返回对象:winform](../_.html#winform)

标准库中所有控件都拥有此同名函数用于返回控件所在窗�?

窗口对象实现了同名函数用于返回窗口自�?
### staticObject.getParent()

返回父窗�?
[返回对象:staticObject](static.html#staticObject)

### staticObject.getPos()

返回相对父窗口客户区的坐�?�?�?

参数为true返回屏幕坐标,�?�?

x,y,cx,cy=win.getPos(hwnd)

### staticObject.getRect()

控件区块位置(::RECT结构�?

### staticObject.getRect(true)

控件屏幕区块位置(::RECT结构�?

### staticObject.getRoot()

获取顶层父窗口，这个函数会查�?orphanWindow 的父窗口

### staticObject.group()

将在此控件范围内的所有其他控件设为此控件的子窗口

### staticObject.height

高度

### staticObject.hide

当前控件窗口是否隐藏�?
仅检查当前窗口的可见性样式（窗口 是否移除�?\_WS\_VISIBLE 样式）�?
不考虑父窗口是否可见，不考虑是否被其他窗口遮挡�?
如果需要同时判断父窗口的可见性，应改�?win.isVisible 函数�?
### staticObject.hwnd

控件句柄

### staticObject.id

控件ID

### staticObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/)

使窗口绘图区无效

### staticObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/,0)

使窗口绘图区无效

不刷新背�?
### staticObject.isDialogMessage

```aardio aardio
staticObject.isDialogMessage = function(hParent,msg){/*在控件范围内替代父窗口的 isDialogMessage�?可用于在控件范围内屏蔽对话框快捷键�?可用于禁�?tab 控制键的多行文本框支持按 tab 输入制表�?/}

```

### staticObject.isForm

标准库中所有控件以及窗体对象都拥有此同名函�?
窗体返回true,控件返回false

### staticObject.left

左侧坐标

### staticObject.messageOnly()

将窗口转换为message-only window

该窗口不可见,仅用于消息分�?
### staticObject.modifyStyle(remove,add,swpFlags)

修改窗口样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### staticObject.modifyStyleEx(remove,add,swpFlags)

修改窗口扩展样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS\_EX_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS\_EX_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### staticObject.msgErr()

显示错误提示�?
请先调用win.dlg.message.install安装此函�?
### staticObject.msgFrown()

显示皱眉图标提示�?
请先调用win.dlg.message.install安装此函�?
### staticObject.msgGreat()

显示竖大拇指图标提示�?
请先调用win.dlg.message.install安装此函�?
### staticObject.msgInfo()

显示提示�?
请先调用win.dlg.message.install安装此函�?
### staticObject.msgOk()

显示正确提示�?
请先调用win.dlg.message.install安装此函�?
### staticObject.msgSmile()

显示微笑图标提示�?
请先调用win.dlg.message.install安装此函�?
### staticObject.msgSorry()

显示倒竖大拇指图标提示框

请先调用win.dlg.message.install安装此函�?
### staticObject.msgWarn()

显示警告提示�?
请先调用win.dlg.message.install安装此函�?
### staticObject.msgbox("字符串参�?)

弹出对话�?可选用参数@2指定标题

### staticObject.msgboxErr("字符串参�?)

弹出错误对话�?可选用参数@2指定标题

### staticObject.msgboxTest("字符串参�?)

弹出询问对话�?可选用参数@2指定标题

### staticObject.onDestroy

```aardio aardio
staticObject.onDestroy = function(){
    /*窗口销毁前触发*/
}

```

### staticObject.oncommand

```aardio aardio
staticObject.oncommand = function(id,event){
    /*命令事件触发*/
}

```

### staticObject.onnotify

```aardio aardio
staticObject.onnotify = function(id,code,ptr){
    /*通知事件触发*/
}

```

### staticObject.orphanWindow

如果当前是子窗口,

移除窗口的WS\_CHILD样式，使窗口孤立出来悬浮于原位置,

悬浮窗口如影随形的跟随父窗口移动或改变大�?控件原来的固定边距等参数仍然有效

### staticObject.orphanWindow(transparent,hwndBuddy,borderless)

创建悬浮窗口�?
悬浮窗口是模仿子窗口外观效果的独立窗口，父窗口可自动调整子窗口到设定位置�?
可选参�?@transparent �?true 则转换为分层透明窗口�?
可选利�?@hwndBuddy 参数指定外部进程窗口句柄的并附加在内部控件上以实现相同的效果�?
伙伴窗口总是会保持在悬浮窗口前面，并保持相同的大小、位置�?
可重复调用此函数更换伙伴窗口，旧的伙伴窗口必须自行关闭�?
可选指�?@borderless 参数 �?true 以移�?@hwndBuddy 的窗口边框�?
### staticObject.postMessage(msg,wParam,lParam)

投递窗口消息到消息队列�?
此函数用法请参�?::User32.PostMessage

### staticObject.preadjust

```aardio aardio
staticObject.preadjust = function( cx,cy,wParam ) {
    /*窗口缩放后重绘前、触�?adjust 事件之前触发此事件�?所�?win.form 创建的窗体和控件都支持此事件,
�?adjust 事件不同，对 preadjust 重复赋值则覆盖而不是追加事件�?
cx 参数为窗口宽�?cy 参数为窗口高�?
wParam �?_WM_SIZE 消息参数�?/
};

```

### staticObject.publish("字符串参�?,)

在窗口所在界面线程发布消�?

运行界面线程所有所有调用subscribe函数订阅此消息的函数,

可添加任意个触发参数

### staticObject.redraw()

刷新

### staticObject.redrawTransparent()

刷新

透明背景时请使用此函数替代redraw()

### staticObject.reduce(array,callback,debounce)

```aardio aardio
staticObject.reduce(
    {/*在这里指定要遍历处理每个元素的数组或�?
并在回调函数中返回每次需要间隔的延时,以毫秒为单位,返回0或空值中断处�?
回调参数为下一个元素的值和索引,处理完后回调参数为null,
如果此时未返回null�?退出处理函�?将返回第一个元素继续遍�?/},
    function(value,index){
        if(value){
            return 50
        }
    }
)

```

```aardio aardio
staticObject.reduce(
    {/*@array 参数指定要循环处理每个元素的数组或表�?@array 指定�?false 则取消之前创建的防抖单例循环�?
@callback 指定回调函数�?回调函数中可返回本次间隔延时，以毫秒为单位�?返回 0、null、false、以及不能转换为�?0 数的值中断处理�?回调参数为下一个元素的值和索引,处理到数组尾部时回调参数�?null,
如果此时仍然返回可转换为�?0 数的�?将转到第一个数组元素重复循�?@callback 指定回调函数�?
@debounce 指定是否创建为防抖单例循环，默认�?true�?/},
    function(value,index){
        if(value){
            return 50
        }
    }
)

```

### staticObject.reloadScale()

按设计时位置参数、重新调整控件位置以适应窗口当前缩放比例�?
父窗口缩放时会自动执行此操作�?
默认在启动窗口消息循环时会自适应调整所有控件�?
所以在启动消息循环前添加控件不必调用此函数

### staticObject.resize(宽度,高度)

如果指定了参数则调整窗口大小,

无论是否实际调整窗口大小,发�?\_WM\_SIZE 消息给窗�?
### staticObject.right

右侧坐标

### staticObject.saveScale()

根据控件当前位置、缩放比例，更新控件的设计时位置参数�?
以避免下次窗口缩放自适应调整控件当前位置更改被清除，

控件所有调整位置的属性或成员函数已自动调用此函数�?
### staticObject.sendMessage(msg,wParam,lParam)

发送窗口消�?
此函数用法请参�?::User32.SendMessage

### staticObject.setFocus()

设置焦点

### staticObject.setFont(指定字体)

指定 LOGFONT 字体对象,或逻辑字体句柄

如果不指�?point 值并指定 h 值，字体会按控件�?DPI 缩放设置自动缩放�?
### staticObject.setFont(混入字体属�?

```aardio aardio
staticObject.setFont(h=-12;name="Tahoma");

```

### staticObject.setInterval(回调函数,延时毫秒�?...)

```aardio aardio
staticObject.setInterval(回调函数,延时毫秒�?...setInterval(
    function(){
        /*参数@1指定执行函数,参数@2指定执行间隔�?可选指定一个或多个回调参数，不指定回调参数则默认为:
 hwnd,message,timerId,tick,

如果在定时器中执行了win.delay等继续消息循环的代码�?在定时器退出前不会再触发同一定时器（重入）�?
定时器回调函数返回数值可修改时间间隔,
返回false取消该定时器*/
    },1000
)

```

### staticObject.setParent(控件对象)

改变父窗�?
### staticObject.setPos(x坐标,y坐标,�?�?插入位置,参数)

调整窗口位置或排�?所有参数可�?
同时指定x,y坐标则移动位�?
同时指定宽高则改变大�?
指定插入位置(句柄或\_HWND前缀常量)则调整Z�?
### staticObject.setRect(rc)

设置控件区块位置(::RECT结构�?

### staticObject.setRect(rc,true)

设置控件屏幕区块位置(::RECT结构�?

### staticObject.setRedraw(false)

禁止重绘

### staticObject.setRedraw(true)

恢复重绘

### staticObject.setTimeout(函数或代�?延时,其他附加参数)

推迟执行指定的函数或代码

此函数异步执行参数中指定的函数，不会阻塞当前代码继续执行�?
延时参数是可选参数，以毫秒为单位，默认为0毫秒

可选用附加参数指定调用延时函数的实�?
返回值为定时器ID

### staticObject.show(true)

显示控件

### staticObject.tabNext()

[返回对象:staticObject](static.html#staticObject)

### staticObject.tabNext(移动焦点,是否反向)

获取下一个支持tab控制焦点的控�?
参数@1为true会自动移动焦点到该控�?
参数@2为true则获取上一个控�?否则获取下一个控�?
### staticObject.text

控件文本

### staticObject.theme

外观主题,例如

winform.button.theme = "Explorer"

winform.button.theme = false

### staticObject.threadCallable()

开启此控件的跨线程调用功能

### staticObject.top

顶部坐标

### staticObject.translateAccelerator

```aardio aardio
staticObject.translateAccelerator = function(msg){
    if(  msg.wParam == 0x20/*_VK_SPACE*/ & msg.message = 0x101/*_WM_KEYUP*/){
        return true;/*返回是否快捷�?适用窗体或普通控件对�?仅当前窗口内的按键触发此事件

msg 参数为包含窗口按键消息的 ::MSG 结构�?/
    }
}

```

### staticObject.translateCommand()

允许转发转发子窗口的命令（\_WM\_COMMAND）与通知（\_WM\_NOTIFY）消息，

避免子窗�?oncommand，onnotify 等回调失效�?
同时会处理子窗口�?\_WM\_CTLCOLORSTATIC 等消息，

以避免部分外观属性失�?
### staticObject.tryCreateEmbed

创建嵌入控件,返回控件容器对象,

容器对象�?\_object 成员是创建的 COM 对象,

容器对象可通过添加成员函数响应 COM 对象事件�?
容器对象的主要作用是充当访问 COM 对象的中间代理对象�?
通常使用 util.metaProperty 为容器对象添加属性元表，

属性元表可拦截属性、函数调用并调用 \_object 对象,

createEmbedEx 返回的容器已添加默认代理以直接访�?COM 对象

### staticObject.tryCreateEmbed()

[返回对象:embedObject](../../../com/_.html#embedObject)

### staticObject.tryCreateEmbed(clsId,embedObj)

创建嵌入控件,返回控件容器对象,

容器对象�?\_object 成员是创建的 COM 对象,

容器对象可通过添加成员函数响应 COM 对象事件�?
容器对象的主要作用是充当访问 COM 对象的中间代理对�?

@clsId 指定控件 CLSID,

可选在参数@2中指�?COM 对象绑定的容器对�?
成功返回容器对象,失败返回false,错误信息

### staticObject.update()

重绘invalidate函数指定的区�?
### staticObject.valid

窗口是否有效�?
窗口未关闭返�?true �?
窗口已关闭或正在关闭返回 false

### staticObject.wait(等待函数,超时,延时间隔)

循环执行等待函数,并等待返回�?
直到等待函数返回非空�?或存在第二个返回�?或当前窗口关�?
等待函数返回的值就是wait函数的返回�?

如果指定超时,超过指定毫秒时返回null,

除等待函数以�?所有参数可�?
### staticObject.width

宽度

### staticObject.wndproc

```aardio aardio
staticObject.wndproc = function(hwnd,message,wParam,lParam){
    /*窗口消息回调，返回任意非null值阻止默认回�?wndproc重复赋值时追加函数而不是覆盖之前的回调
设为null添除所有消息回调函�?wndproc也可以是一个表,键要为处理的消息,值为对应的消息回调函�?/
}

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/win/ui/ctrl/static.md)

