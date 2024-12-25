[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# win.ui.statusbar 库模块帮助文�?
## statusbarObject 成员列表

### statusbarObject.addItem(文本, /\*宽度\*/)

创建一个状态栏分块

### statusbarObject.bgcolor

背景颜色

### statusbarObject.bottom

底部坐标�?
只能获取，修改无�?
注意状态栏是默认已经做�?DPI 缩放的，

所以请�?winform.enableDpiScaling("init"); 以后使用这些属�?
### statusbarObject.capture

是否捕获全局鼠标消息

### statusbarObject.className

运行时类�?
### statusbarObject.close()

清除状态栏

### statusbarObject.cls

设计时类�?
### statusbarObject.count()

获取分块的数�?
### statusbarObject.disabled

是否禁用

### statusbarObject.getBorders()

返回上下边框，左右边框，间隔边框宽度�?
这个值实际测试基本都是返�?2,0,2

### statusbarObject.getFont(true)

返回控件字体，返回值为 ::LOGFONT 结构�?
[返回对象:logfontObject](#logfontObject)

### statusbarObject.getForm()

如果是窗体返回自�?
如果是控件则返回 \_parentForm

[返回对象:winform](_.html#winform)

### statusbarObject.getItemRect()

返回表示项目区块位置�?::RECT 结构体，

参数指定�?1 开始的项目索引

[返回对象:rectObject](../../global/_.html#rectObject)

### statusbarObject.getItemWidth(第几个分�?

获取指定分块的宽�?分块�?1 开�?
### statusbarObject.getParent()

返回父窗�?
[返回对象:winform](_.html#winform)

### statusbarObject.getPos()

返回相对父窗口客户区的坐�?�?�?

参数�?true 返回屏幕坐标,�?�?
注意状态栏是默认已经做�?DPI 缩放的，

所以请�?winform.enableDpiScaling("init"); 以后使用这些属�?
### statusbarObject.getRect()

控件区块位置，返回值为 ::RECT结构�?
[返回对象:rectObject](../../global/_.html#rectObject)

### statusbarObject.getRect(true)

控件屏幕区块位置，返回值为 ::RECT结构�?
### statusbarObject.getRoot()

获取顶层父窗�?
### statusbarObject.getText()

获取状态栏的文�?无分�?

### statusbarObject.getText(第几个分�?

获取指定分块的文�?分块�?1 开�?
### statusbarObject.height

获取时返回状态栏实际高度�?
修改高度无效，请改用 setMinHeight 函数�?
注意状态栏是默认已经做�?DPI 缩放的，

所以请�?winform.enableDpiScaling("init"); 以后使用这些属�?
### statusbarObject.hide

控件是否隐藏

### statusbarObject.hwnd

控件句柄

### statusbarObject.insertItem(文本, /\*插入位置\*/, /\*宽度\*/)

插入一个状态栏分块,插入位置�?1 开�?
### statusbarObject.left

左侧坐标�?
只能获取，修改无�?
注意状态栏是默认已经做�?DPI 缩放的，

所以请�?winform.enableDpiScaling("init"); 以后使用这些属�?
### statusbarObject.modifyStyle(移除样式,添加样式)

所有参数可�?默认�?

使用 _TBSTYLE_ 前缀常量表示样式

### statusbarObject.onDestroy

```aardio aardio
statusbarObject.onDestroy = function(){
    /*窗口销毁前触发*/
}

```

### statusbarObject.onnotify

```aardio aardio
statusbarObject.onnotify = function(id,code,ptr){
    /*通知事件触发*/
}

```

### statusbarObject.postMessage(msg,wParam,lParam)

投递窗口消息到消息队列�?
此函数用法请参�?::User32.PostMessage

### statusbarObject.redraw()

刷新

### statusbarObject.redrawTransparent()

刷新

透明背景时请使用此函数替�?redraw()

### statusbarObject.right

右侧坐标�?
只能获取，修改无�?
注意状态栏是默认已经做�?DPI 缩放的，

所以请�?winform.enableDpiScaling("init"); 以后使用这些属�?
### statusbarObject.sendMessage(msg,wParam,lParam)

发送窗口消�?
此函数用法请参�?::User32.SendMessage

### statusbarObject.setFont(指定字体)

指定LOGFONT字体对象,或逻辑字体句柄

### statusbarObject.setItemWidth(第几个分�? /\*宽度\*/)

设置指定分块的宽�?分块�?1 开�?
### statusbarObject.setMinHeight()

设置状态栏内部最小高度，

此高度已包含上下边框宽度（通常�?2 个像素）�?
此函数已自动支持 DPI 缩放

### statusbarObject.setRedraw(false)

禁止重绘

### statusbarObject.setRedraw(true)

恢复重绘

### statusbarObject.setText(文本)

设置状态栏的文�?无分�?

### statusbarObject.setText(文本, /\*第几个分块\*/)

设置指定分块的文�?分块�?1 开�?
### statusbarObject.show(true)

显示控件

### statusbarObject.theme

外观主题,例如

winform.button.theme = "Explorer"

winform.button.theme = false

### statusbarObject.top

顶部坐标�?
只能获取，修改无�?
注意状态栏是默认已经做�?DPI 缩放的，

所以请�?winform.enableDpiScaling("init"); 以后使用这些属�?
### statusbarObject.width

状态栏宽度�?
只能获取，修改无�?
注意状态栏是默认已经做�?DPI 缩放的，

所以请�?winform.enableDpiScaling("init"); 以后使用这些属�?
### statusbarObject.wndproc

```aardio aardio
statusbarObject.wndproc = function(hwnd,message,wParam,lParam){
    /*窗口消息回调，返回任意非null值阻止默认回�?wndproc重复赋值时追加函数而不是覆盖之前的回调
设为null添除所有消息回调函�?wndproc也可以是一个表,键要为处理的消息,值为对应的消息回调函�?/
}

```

## win.ui 成员列表

### win.ui.statusbar

状态栏控件

### win.ui.statusbar()

[返回对象:statusbarObject](#statusbarObject)

### win.ui.statusbar(父窗�?

创建一个状态栏

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/win/ui/statusbar.md)

