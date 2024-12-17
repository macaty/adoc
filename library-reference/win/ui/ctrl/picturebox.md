[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# win.ui.ctrl.picturebox 库模块帮助文�?
## win.ui.ctrl 成员列表

### win.ui.ctrl.picturebox()

图片控件

[返回对象:pictureboxObject](#pictureboxObject)

## pictureboxObject 成员列表

### pictureboxObject.\_parentForm

创建该控件的父窗口（win.form对象�?

设计时窗体容器是所有拖放在窗体上的控件�?\_parentForm,

即使窗口移除子窗口样式、更改父子关系，或以 orphanWindow显示,

控件�?\_parentForm 始终都不会改�?
[返回对象:winform](../_.html#winform)

### pictureboxObject.adjust

```aardio aardio
pictureboxObject.adjust = function( cx,cy,wParam ) {
    /*窗口缩放时会自动触发此函数�?cx 参数为窗口宽�?cy 参数为窗口高�?
wParam 参数请参�?_WM_SIZE 消息参数说明,一般不用管�?
所�?win.form 创建的窗体和控件都支持此事件,
重复赋值只会追加而不会覆盖此事件�?一般不建议添加一�?wndproc 仅仅是为了处�? _WM_SIZE 消息�?定义 adjust 事件是更好的选择�?
可主动调用此事件,省略参数�?cx,cy 参数默认设为窗口大小*/
};

```

### pictureboxObject.autosize

是否允许控件自适应图片大小

设置center属性为true�?autosize属性无�?
### pictureboxObject.bottom

底部坐标

### pictureboxObject.capture

是否捕获全局鼠标消息

### pictureboxObject.center

图像居中显示,并禁用图象缩�?

禁止控件自动调整大小

### pictureboxObject.className

运行时类�?
### pictureboxObject.clear()

清空图像，并释放控件加载的位图或图标句柄�?
控件销毁前会自动调用此函数

注意�?
如果位图包含透明通道，控件会使用复制的位图副本�?
调用者必须自行释放传入的位图句柄�?
gdip.bitmap 复制的位图句柄就会有这个问题�?
com.picture 加载�?GIF 图像无此问题

改用 plus 控件没有这些麻烦

### pictureboxObject.clientRect

获取控件客户区块位置(::RECT结构�?

### pictureboxObject.close()

关闭控件

### pictureboxObject.cls

设计时类�?
### pictureboxObject.disabled

是否禁用

### pictureboxObject.getBitmap()

返回位图句柄或图标句柄�?
返回�?1 为图标句柄则返回�?2 �?1/\*\_IMAGE\_ICON\*/

返回�?1 为位图句柄则返回�?2 �?0/\*\_IMAGE\_BITMAP\*/

### pictureboxObject.getClientRect()

控件客户区块位置(::RECT结构�?

[返回对象:rectObject](../../../global/_.html#rectObject)

### pictureboxObject.getParent()

返回父窗�?
[返回对象:staticObject](static.html#staticObject)

### pictureboxObject.getPos()

返回相对坐标,�?�?
x,y,cx,cy=win.getPos(hwnd)

### pictureboxObject.getRect()

控件区块位置(::RECT结构�?

### pictureboxObject.getRect(true)

控件屏幕区块位置(::RECT结构�?

### pictureboxObject.height

高度

### pictureboxObject.hide

控件是否隐藏

### pictureboxObject.hwnd

控件句柄

### pictureboxObject.id

控件ID

### pictureboxObject.image

按钮图片或图�?
赋值必须是图片文件路径或数�?
位图句柄由窗体负责销�?
取值时返回位图句柄

### pictureboxObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/)

使窗口绘图区无效

### pictureboxObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/,0)

使窗口绘图区无效

不刷新背�?
### pictureboxObject.left

左侧坐标

### pictureboxObject.modifyStyle(remove,add,swpFlags)

修改窗口样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### pictureboxObject.modifyStyleEx(remove,add,swpFlags)

修改窗口扩展样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS\_EX_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS\_EX_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### pictureboxObject.orphanWindow(transparent,hwndBuddy,borderless)

创建悬浮窗口�?
悬浮窗口是模仿子窗口外观效果的独立窗口，父窗口可自动调整子窗口到设定位置�?
可选参�?@transparent �?true 则转换为分层透明窗口�?
可选利�?@hwndBuddy 参数指定外部进程窗口句柄的并附加在内部控件上以实现相同的效果�?
伙伴窗口总是会保持在悬浮窗口前面，并保持相同的大小、位置�?
可重复调用此函数更换伙伴窗口，旧的伙伴窗口必须自行关闭�?
可选指�?@borderless 参数 �?true 以移�?@hwndBuddy 的窗口边框�?
### pictureboxObject.postMessage(msg,wParam,lParam)

投递窗口消息到消息队列�?
此函数用法请参�?::User32.PostMessage

### pictureboxObject.redraw()

刷新

### pictureboxObject.reloadScale()

按设计时位置参数、重新调整控件位置以适应窗口当前缩放比例�?
父窗口缩放时会自动执行此操作�?
默认在启动窗口消息循环时会自适应调整所有控件�?
所以在启动消息循环前添加控件不必调用此函数�?
### pictureboxObject.right

右侧坐标

### pictureboxObject.saveScale()

根据控件当前位置、缩放比例，更新控件的设计时位置参数�?
以避免下次窗口缩放自适应调整控件当前位置更改被清除，

控件所有调整位置的属性或成员函数已自动调用此函数�?
### pictureboxObject.saveScale(scaleX,scaleY,dpiScaleX,dpiScaleY)

根据控件当前的运行时位置更新设计时大小\\如果控件允许自动缩放，窗口缩放时依据设计时大小按比例缩放

所有参数可省略,并且不建议写参数

### pictureboxObject.sendMessage(msg,wParam,lParam)

发送窗口消�?
此函数用法请参�?::User32.SendMessage

### pictureboxObject.setBitmap(图片句柄)

设置图片

成功返回 true，自动销毁原来的位图�?
注意�?
如果位图包含透明通道，控件会使用复制的位图副本�?
调用者必须自行释放传入的位图句柄�?
可比�?getBitmap 返回的句柄与设置的句柄验证此问题

gdip.bitmap 复制的位图句柄就会有这个问题�?
com.picture 加载�?GIF 图像无此问题

改用 plus 控件没有这些麻烦

### pictureboxObject.setBitmap(图片句柄,false)

设置图片

如果参数 @2 恒等�?false �?
则成功返回控件原来的位图或图标句�?
### pictureboxObject.setFocus()

设置焦点

### pictureboxObject.setIcon(图标句柄)

设置图标

成功返回 true，自动销毁原来的位图�?
### pictureboxObject.setIcon(图标句柄,false)

设置图标

如果参数 @2 恒等�?false �?
则成功返回控件原来的位图或图标句�?
### pictureboxObject.setParent(控件对象)

改变父窗�?
### pictureboxObject.setPos(x坐标,y坐标,�?�?插入位置,参数)

调整窗口位置或排�?所有参数可�?
同时指定x,y坐标则移动位�?
同时指定宽高则改变大�?
指定插入位置(句柄或\_HWND前缀常量)则调整Z�?
### pictureboxObject.setRect(rc)

设置控件区块位置(::RECT结构�?

### pictureboxObject.setRect(rc,true)

设置控件屏幕区块位置(::RECT结构�?

### pictureboxObject.show(true)

显示控件

### pictureboxObject.theme

外观主题,例如

winform.button.theme = "Explorer"

winform.button.theme = false

### pictureboxObject.top

顶部坐标

### pictureboxObject.update()

重绘invalidate函数指定的区�?
### pictureboxObject.width

宽度

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/win/ui/ctrl/picturebox.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/win/ui/ctrl/picturebox.md')

