[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# win.ui.toolbar 库模块帮助文�?
## toolbarButtonObject 成员列表

### toolbarButtonObject.checked

是否选中

### toolbarButtonObject.click()

点击按钮

### toolbarButtonObject.delete()

删除按钮

### toolbarButtonObject.disabled

是否禁用

### toolbarButtonObject.getInfo( \_TBIF )

获取TBBUTTONINFO结构�?
### toolbarButtonObject.getRect()

返回按钮区块

[返回对象:rectObject](../../global/_.html#rectObject)

### toolbarButtonObject.id

命令ID

### toolbarButtonObject.index()

返回按钮索引

### toolbarButtonObject.setInfo( )

设置TBBUTTONINFO结构�?可指定部分字�?
### toolbarButtonObject.state

读写按钮状�?
### toolbarButtonObject.text

按钮文本

## toolbarObject 成员列表

### toolbarObject.add()

添加一个分隔条

[返回对象:toolbarButtonObject](#toolbarButtonObject)

### toolbarObject.add(标题,回调函数,图像索引,可选指定命令ID)

```aardio aardio
toolbarObject.add(
    "文字",
    function (id) {

    },1
)

```

### toolbarObject.adjust()

重新设置工具栏大�?
### toolbarObject.bottom

底部坐标�?
只能获取，修改无�?
注意工具条是默认已经做过 DPI 缩放的，

所以请�?winform.enableDpiScaling("init"); 以后使用这些属�?
### toolbarObject.buttons\[1索引\]

返回指定的按钮对�?
### toolbarObject.capture

是否捕获全局鼠标消息

### toolbarObject.className

运行时类�?
### toolbarObject.cls

设计时类�?
### toolbarObject.create(tParam)

创建工具�?注意工具条会占用父窗口上的空�?

可选传�?@tParam 参数�?可包�?style,exstyle 等样式参�?
可用样式可参�?

[https://docs.microsoft.com/en-us/windows/win32/controls/toolbar-control-and-button-styles](https://docs.microsoft.com/en-us/windows/win32/controls/toolbar-control-and-button-styles)

### toolbarObject.disabled

是否禁用

### toolbarObject.getButton()

[返回对象:toolbarButtonObject](#toolbarButtonObject)

### toolbarObject.getButton(索引)

返回按钮对象

### toolbarObject.getButtonById()

[返回对象:toolbarButtonObject](#toolbarButtonObject)

### toolbarObject.getButtonById(idCommand)

返回按钮对象

### toolbarObject.getClientRect()

控件客户区块位置，返回值为 ::RECT结构�?
[返回对象:rectObject](../../global/_.html#rectObject)

### toolbarObject.getExtended()

获取工具条扩展样�?
### toolbarObject.getExtended(exstyle)

获取工具条指定扩展样�?
### toolbarObject.getFont(true)

返回控件字体，返回值为 ::LOGFONT 结构�?
[返回对象:logfontObject](#logfontObject)

### toolbarObject.getForm()

如果是窗体返回自�?
如果是控件则返回 \_parentForm

[返回对象:winform](_.html#winform)

### toolbarObject.getNotifyInfo(ptr)

在通知回调中获�?PNMTOOLBAR 结构体，

ptr �?onnotify 回调传过来的指针参数

### toolbarObject.getParent()

返回父窗�?
[返回对象:winform](_.html#winform)

### toolbarObject.getPos()

返回相对父窗口客户区的坐�?�?�?

参数�?true 返回屏幕坐标,�?�?
注意工具条是默认已经做过 DPI 缩放的，

所以请�?winform.enableDpiScaling("init"); 以后使用这些属�?
### toolbarObject.getRect()

控件区块位置，返回值为 ::RECT结构�?
[返回对象:rectObject](../../global/_.html#rectObject)

### toolbarObject.getRect(true)

控件屏幕区块位置，返回值为 ::RECT结构�?
### toolbarObject.getRoot()

获取顶层父窗�?
### toolbarObject.height

获取时返回工具条实际高度�?
只能获取，修改无效�?
注意工具条是默认已经做过 DPI 缩放的，

所以请�?winform.enableDpiScaling("init"); 以后使用这些属�?
### toolbarObject.hide

控件是否隐藏

### toolbarObject.hwnd

控件句柄

### toolbarObject.imageList

指定工具条控件的图像列表�?
指定的图像列表支�?DPI 自适应缩放

发�?\_CCM\_DPISCALE 消息且其他参数为 0 可关�?DPI 自适应

### toolbarObject.left

左侧坐标�?
只能获取，修改无�?
注意工具条是默认已经做过 DPI 缩放的，

所以请�?winform.enableDpiScaling("init"); 以后使用这些属�?
### toolbarObject.modifyStyle(移除样式,添加样式)

所有参数可�?默认�?

使用 _TBSTYLE_ 前缀常量表示样式

### toolbarObject.onDestroy

```aardio aardio
toolbarObject.onDestroy = function(){
    /*窗口销毁前触发*/
}

```

### toolbarObject.onnotify

```aardio aardio
toolbarObject.onnotify = function(id,code,ptr){
    /*通知事件触发*/
}

```

### toolbarObject.postMessage(msg,wParam,lParam)

投递窗口消息到消息队列�?
此函数用法请参�?::User32.PostMessage

### toolbarObject.redraw()

刷新

### toolbarObject.redrawTransparent()

刷新

透明背景时请使用此函数替代redraw()

### toolbarObject.right

右侧坐标�?
只能获取，修改无�?
注意工具条是默认已经做过 DPI 缩放的，

所以请�?winform.enableDpiScaling("init"); 以后使用这些属�?
### toolbarObject.sendMessage(msg,wParam,lParam)

发送窗口消�?
此函数用法请参�?::User32.SendMessage

### toolbarObject.setExtended(exstyle)

启用工具条指定扩展样�?
### toolbarObject.setExtended(exstyle,false)

取消工具条指定扩展样�?
### toolbarObject.setFont(指定字体)

指定LOGFONT字体对象,或逻辑字体句柄

### toolbarObject.setPos(x坐标,y坐标,�?�?插入位置,参数)

调整窗口位置或排�?所有参数可�?
同时指定x,y坐标则移动位�?
同时指定宽高则改变大�?
指定插入位置(句柄或\_HWND前缀常量)则调整Z�?
### toolbarObject.setRect(rc)

设置控件区块位置，返回值为 ::RECT结构�?
### toolbarObject.setRect(rc,true)

设置控件屏幕区块位置，返回值为 ::RECT结构�?
### toolbarObject.setRedraw(false)

禁止重绘

### toolbarObject.setRedraw(true)

恢复重绘

### toolbarObject.show(true)

显示控件

### toolbarObject.showLabel

是否在按钮上显示文字

### toolbarObject.style

工具栏样�?数�?

使用 _TBSTYLE_ 前缀常量表示样式,

也支�?_CCS_ 前缀的样式常�?

直接设置此样式会覆盖工具条原来的一些默认样�?

例如 让工具条显示在顶部的 \_CCS\_TOP,这会导致工具条移到底�?

建议�?modifyStyle 修改样式可避免此问题

### toolbarObject.theme

外观主题,例如

winform.button.theme = "Explorer"

winform.button.theme = false

### toolbarObject.top

顶部坐标�?
只能获取，修改无�?
注意工具条是默认已经做过 DPI 缩放的，

所以请�?winform.enableDpiScaling("init"); 以后使用这些属�?
### toolbarObject.width

工具条宽度�?
只能获取，修改无�?
注意工具条是默认已经做过 DPI 缩放的，

所以请�?winform.enableDpiScaling("init"); 以后使用这些属�?
### toolbarObject.wndproc

```aardio aardio
toolbarObject.wndproc = function(hwnd,message,wParam,lParam){
    /*窗口消息回调，返回任意非null值阻止默认回�?wndproc重复赋值时追加函数而不是覆盖之前的回调
设为null添除所有消息回调函�?wndproc也可以是一个表,键要为处理的消息,值为对应的消息回调函�?/
}

```

## toolbarObject.buttons 成员列表

### toolbarObject.buttons.?

[返回对象:toolbarButtonObject](#toolbarButtonObject)

## win.ui 成员列表

### win.ui.toolbar()

[返回对象:toolbarObject](#toolbarObject)

### win.ui.toolbar(父窗�?

工具条控件�?
此控件不建议使用，请改用高级选项�?win.ui.tabs ），

高级选项卡可以更好地支持字体图标�?DPI 缩放�?
### 自动完成常量

\_CCS\_ADJUSTABLE=0x20

\_CCS\_BOTTOM=3

\_CCS\_LEFT=0x81

\_CCS\_NODIVIDER=0x40

\_CCS\_NOMOVEX=0x82

\_CCS\_NOMOVEY=2

\_CCS\_NOPARENTALIGN=8

\_CCS\_NORESIZE=4

\_CCS\_RIGHT=0x83

\_CCS\_TOP=1

\_CCS\_VERT=0x80

\_TBIF\_COMMAND=0x20

\_TBIF\_IMAGE=1

\_TBIF\_LPARAM=0x10

\_TBIF\_SIZE=0x40

\_TBIF\_STATE=4

\_TBIF\_STYLE=8

\_TBIF\_TEXT=2

\_TBSTYLE\_ALTDRAG=0x400

\_TBSTYLE\_AUTOSIZE=0x10

\_TBSTYLE\_BUTTON=0

\_TBSTYLE\_CHECK=2

\_TBSTYLE\_CHECKGROUP=6

\_TBSTYLE\_CUSTOMERASE=0x2000

\_TBSTYLE\_DROPDOWN=8

\_TBSTYLE\_FLAT=0x800

\_TBSTYLE\_GROUP=4

\_TBSTYLE\_LIST=0x1000

\_TBSTYLE\_NOPREFIX=0x20

\_TBSTYLE\_REGISTERDROP=0x4000

\_TBSTYLE\_SEP=1

\_TBSTYLE\_TOOLTIPS=0x100

\_TBSTYLE\_TRANSPARENT=0x8000

\_TBSTYLE\_WRAPABLE=0x200

\_TB\_CHANGEBITMAP=0x42B

\_TB\_GETBITMAP=0x42C

\_TB\_GETBUTTONSIZE=0x43A

\_TB\_GETBUTTONTEXT=0x42D

\_TB\_GETDISABLEDIMAGELIST=0x437

\_TB\_GETRECT=0x433

\_TB\_GETSTYLE=0x439

\_TB\_GETTOOLTIPS=0x423

\_TB\_SETBUTTONWIDTH=0x43B

\_TB\_SETDISABLEDIMAGELIST=0x436

\_TB\_SETSTYLE=0x438

\_TB\_SETTOOLTIPS=0x424

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/win/ui/toolbar.md)

