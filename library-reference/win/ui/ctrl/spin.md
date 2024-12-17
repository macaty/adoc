[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# win.ui.ctrl.spin 库模块帮助文�?
## win.ui.ctrl 成员列表

### win.ui.ctrl.spin()

滚动选框控件

[返回对象:spinbuttonObject](#spinbuttonObject)

## spinbuttonObject 成员列表

### spinbuttonObject.\_parentForm

创建该控件的父窗口（win.form对象�?

设计时窗体容器是所有拖放在窗体上的控件�?\_parentForm,

即使窗口移除子窗口样式、更改父子关系，或以 orphanWindow显示,

控件�?\_parentForm 始终都不会改�?
[返回对象:winform](../_.html#winform)

### spinbuttonObject.addCtrl

```aardio aardio
spinbuttonObject.addCtrl(
    button={ cls="button";text="button";left=33;top=32;right=126;bottom=81;autoResize=false }
)

```

### spinbuttonObject.base

显示数值进制基�?10�?6

### spinbuttonObject.bottom

底部坐标

### spinbuttonObject.buddy

设置、获取伙伴窗口�?
伙伴窗口必须�?edit 控件（自动启用限制输入数字）�?
spin 控件可放�?edit 控件内部或外部左侧、右侧�?
调整窗口大小时，spin 控件会自动吸附于 edit 控件左侧或右侧�?
如果 spin 控件�?edit 控件左侧，建议添�?align="left" 属性，

如果 spin 控件�?edit 控件右侧，建议添�?align="right" 属�?
[返回对象:editObject](edit.html#editObject)

### spinbuttonObject.capture

是否捕获全局鼠标消息

### spinbuttonObject.className

运行时类�?
### spinbuttonObject.close()

关闭控件窗口

### spinbuttonObject.cls

设计时类�?
### spinbuttonObject.disabled

是否禁用

### spinbuttonObject.getClientRect()

控件客户区块位置(::RECT结构�?

[返回对象:rectObject](../../../global/_.html#rectObject)

### spinbuttonObject.getFont()

控件字体(::LOGFONT结构�?

[返回对象:logfontObject](#logfontObject)

### spinbuttonObject.getParent()

返回父窗�?
[返回对象:spinbuttonObject](#spinbuttonObject)

### spinbuttonObject.getPos()

返回相对坐标,�?�?
### spinbuttonObject.getRect()

控件区块位置(::RECT结构�?

### spinbuttonObject.getRect(true)

控件屏幕区块位置(::RECT结构�?

### spinbuttonObject.height

高度

### spinbuttonObject.hide

控件是否隐藏

### spinbuttonObject.hwnd

控件句柄

### spinbuttonObject.id

控件ID

### spinbuttonObject.inc

设置步长

### spinbuttonObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/)

使窗口绘图区无效

### spinbuttonObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/,0)

使窗口绘图区无效

不刷新背�?
### spinbuttonObject.left

左侧坐标

### spinbuttonObject.modifyStyle(remove,add,swpFlags)

修改窗口样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### spinbuttonObject.modifyStyleEx(remove,add,swpFlags)

修改窗口扩展样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS\_EX_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS\_EX_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### spinbuttonObject.onnotify

```aardio aardio
spinbuttonObject.onnotify = function(id,code,ptr){
    if(code==0xFFFFFD2E/*_UDN_DELTAPOS*/){
        var nmUpDown = ..raw.convert(ptr, {
            struct hdr = ::NMHDR();
            int pos;
            int delta;
        } );
        /*pos为当前位�?delta为增减量,单击向下箭头此值为负数*/
    }
}

```

### spinbuttonObject.pos

当前位置数�?
### spinbuttonObject.postMessage(msg,wParam,lParam)

投递窗口消息到消息队列�?
此函数用法请参�?::User32.PostMessage

### spinbuttonObject.redraw()

刷新

### spinbuttonObject.right

右侧坐标

### spinbuttonObject.sendMessage(msg,wParam,lParam)

发送窗口消�?
此函数用法请参�?::User32.SendMessage

### spinbuttonObject.setFocus()

设置焦点

### spinbuttonObject.setFont(指定字体)

指定LOGFONT字体对象,或逻辑字体句柄

### spinbuttonObject.setFont(混入字体属�?

```aardio aardio
spinbuttonObject.setFont(point=10;name="宋体");

```

### spinbuttonObject.setParent(控件对象)

改变父窗�?
### spinbuttonObject.setPos(x坐标,y坐标,�?�?插入位置,参数)

调整窗口位置或排�?所有参数可�?
同时指定x,y坐标则移动位�?
同时指定宽高则改变大�?
指定插入位置(句柄或\_HWND前缀常量)则调整Z�?
### spinbuttonObject.setRange(最小�?最大�?

设置数值范�?
同时修改pos属性为最小�?
### spinbuttonObject.setRect(rc)

设置控件区块位置(::RECT结构�?

### spinbuttonObject.setRect(rc,true)

设置控件屏幕区块位置(::RECT结构�?

### spinbuttonObject.show(true)

显示控件

### spinbuttonObject.text

控件文本

### spinbuttonObject.theme

外观主题,例如

winform.button.theme = "Explorer"

winform.button.theme = false

### spinbuttonObject.threadCallable()

开启此控件的跨线程调用功能

### spinbuttonObject.top

顶部坐标

### spinbuttonObject.update()

重绘invalidate函数指定的区�?
### spinbuttonObject.width

宽度

### 自动完成常量

\_UDM\_GETACCEL=0x46C

\_UDM\_SETACCEL=0x46B

\_UDN\_DELTAPOS=0xFFFFFD2E

\_UDS\_ALIGNLEFT=8

\_UDS\_ALIGNRIGHT=4

\_UDS\_ARROWKEYS=0x20

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/win/ui/ctrl/spin.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/win/ui/ctrl/spin.md')

