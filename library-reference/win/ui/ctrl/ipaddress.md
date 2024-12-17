[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# win.ui.ctrl.ipaddress 库模块帮助文�?
## win.ui.ctrl 成员列表

### win.ui.ctrl.ipaddress()

IP地址控件

[返回对象:SysIPAddressObject](#SysIPAddressObject)

## SysIPAddressObject 成员列表

### SysIPAddressObject.\_parentForm

创建该控件的父窗口（win.form对象�?

设计时窗体容器是所有拖放在窗体上的控件�?\_parentForm,

即使窗口移除子窗口样式、更改父子关系，或以 orphanWindow显示,

控件�?\_parentForm 始终都不会改�?
[返回对象:winform](../_.html#winform)

### SysIPAddressObject.addCtrl

```aardio aardio
SysIPAddressObject.addCtrl(

    edit ={ cls="edit";left=0;top=0;right=50;bottom=50;autoResize=false ;hide=1;edge=1;  }
)

```

### SysIPAddressObject.address

IP地址数值格�?
### SysIPAddressObject.bottom

底部坐标

### SysIPAddressObject.capture

是否捕获全局鼠标消息

### SysIPAddressObject.className

运行时类�?
### SysIPAddressObject.clear()

清除列表框所有内�?
### SysIPAddressObject.clientRect

获取控件客户区块位置(::RECT结构�?

### SysIPAddressObject.close()

关闭控件�?
### SysIPAddressObject.cls

设计时类�?
### SysIPAddressObject.disabled

是否禁用

### SysIPAddressObject.getClientRect()

控件客户区块位置(::RECT结构�?

[返回对象:rectObject](../../../global/_.html#rectObject)

### SysIPAddressObject.getFont()

控件字体(::LOGFONT结构�?

[返回对象:logfontObject](#logfontObject)

### SysIPAddressObject.getParent()

返回父窗�?
[返回对象:staticObject](static.html#staticObject)

### SysIPAddressObject.getPos()

返回相对坐标,�?�?
x,y,cx,cy=win.getPos(hwnd)

### SysIPAddressObject.getRect()

控件区块位置(::RECT结构�?

### SysIPAddressObject.getRect(true)

控件屏幕区块位置(::RECT结构�?

### SysIPAddressObject.height

高度

### SysIPAddressObject.hwnd

控件句柄

### SysIPAddressObject.id

控件ID

### SysIPAddressObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/)

使窗口绘图区无效

### SysIPAddressObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/,0)

使窗口绘图区无效

不刷新背�?
### SysIPAddressObject.left

左侧坐标

### SysIPAddressObject.modifyStyle(remove,add,swpFlags)

修改窗口样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### SysIPAddressObject.modifyStyleEx(remove,add,swpFlags)

修改窗口扩展样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS\_EX_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS\_EX_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### SysIPAddressObject.onChange()

```aardio aardio
SysIPAddressObject.onChange = function(){
    /*响应事件，文本内容已变更*/
}

```

### SysIPAddressObject.onFieldChanged

```aardio aardio
SysIPAddressObject.onFieldChanged = function(field,value){
    /*IP 变更事件,
field 是变更字段的位置，可能值为1�?�?�?之一�?value 是实际变更字段的数值，字段为空时值为 -1*/
}

```

### SysIPAddressObject.onFocusGot()

```aardio aardio
SysIPAddressObject.onFocusGot = function(){
    /*响应事件，已获得输入焦点*/
}

```

### SysIPAddressObject.onFocusLost()

```aardio aardio
SysIPAddressObject.onFocusLost = function(){
    /*响应事件，已失去输入焦点*/
}

```

### SysIPAddressObject.orphanWindow()

使控件脱离原来的窗口,可以显示在父窗口外面,

但仍然显示在原来的位�?继续如影随形的跟随父窗口移动或改变大�?

控件原来的固定边距等参数仍然有效

### SysIPAddressObject.postMessage(msg,wParam,lParam)

投递窗口消息到消息队列�?
此函数用法请参�?::User32.PostMessage

### SysIPAddressObject.right

右侧坐标

### SysIPAddressObject.sendMessage(msg,wParam,lParam)

发送窗口消�?
此函数用法请参�?::User32.SendMessage

### SysIPAddressObject.setFocus()

设置焦点

### SysIPAddressObject.setFont(指定字体)

指定LOGFONT字体对象,或逻辑字体句柄

### SysIPAddressObject.setFont(混入字体属�?

```aardio aardio
SysIPAddressObject.setFont(point=10;name="宋体");

```

### SysIPAddressObject.setParent(控件对象)

改变父窗�?
### SysIPAddressObject.setPos(x坐标,y坐标,�?�?插入位置,参数)

调整窗口位置或排�?所有参数可�?
同时指定x,y坐标则移动位�?
同时指定宽高则改变大�?
指定插入位置(句柄或\_HWND前缀常量)则调整Z�?
### SysIPAddressObject.setRange(起始IP,结束IP)

设置IP范围

参数可以是文�?也可以分别是指定四组数值的数组

### SysIPAddressObject.setRect(rc)

设置控件区块位置(::RECT结构�?

### SysIPAddressObject.setRect(rc,true)

设置控件屏幕区块位置(::RECT结构�?

### SysIPAddressObject.show(true)

显示控件

### SysIPAddressObject.text

IP 地址文本格式

### SysIPAddressObject.theme

外观主题,例如

winform.button.theme = "Explorer"

winform.button.theme = false

### SysIPAddressObject.threadCallable()

开启此控件的跨线程调用功能

### SysIPAddressObject.top

顶部坐标

### SysIPAddressObject.update()

重绘invalidate函数指定的区�?
### SysIPAddressObject.width

宽度

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/win/ui/ctrl/ipaddress.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/win/ui/ctrl/ipaddress.md')

