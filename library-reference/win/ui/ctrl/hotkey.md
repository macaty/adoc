[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# win.ui.ctrl.hotkey 库模块帮助文�?
## win.ui.ctrl 成员列表

### win.ui.ctrl.hotkey()

热键控件

[返回对象:hotkeyObject](#hotkeyObject)

## hotkeyObject 成员列表

### hotkeyObject.\_parentForm

创建该控件的父窗口（win.form对象�?

设计时窗体容器是所有拖放在窗体上的控件�?\_parentForm,

即使窗口移除子窗口样式、更改父子关系，或以 orphanWindow显示,

控件�?\_parentForm 始终都不会改�?
[返回对象:winform](../_.html#winform)

### hotkeyObject.bottom

底部坐标

### hotkeyObject.capture

是否捕获全局鼠标消息

### hotkeyObject.className

运行时类�?
### hotkeyObject.clientRect

获取控件客户区块位置(::RECT结构�?

### hotkeyObject.close()

关闭控件窗口

### hotkeyObject.cls

设计时类�?
### hotkeyObject.disabled

是否禁用

### hotkeyObject.getClientRect()

控件客户区块位置(::RECT结构�?

[返回对象:rectObject](../../../global/_.html#rectObject)

### hotkeyObject.getFont()

控件字体(::LOGFONT结构�?

[返回对象:logfontObject](#logfontObject)

### hotkeyObject.getParent()

返回父窗�?
[返回对象:staticObject](static.html#staticObject)

### hotkeyObject.getPos()

返回相对坐标,�?�?
x,y,cx,cy=win.getPos(hwnd)

### hotkeyObject.getRect()

控件区块位置(::RECT结构�?

### hotkeyObject.getRect(true)

控件屏幕区块位置(::RECT结构�?

### hotkeyObject.height

高度

### hotkeyObject.hide

控件是否隐藏

### hotkeyObject.hwnd

控件句柄

### hotkeyObject.id

控件ID

### hotkeyObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/)

使窗口绘图区无效

### hotkeyObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/,0)

使窗口绘图区无效

不刷新背�?
### hotkeyObject.left

左侧坐标

### hotkeyObject.modifyStyle(remove,add,swpFlags)

修改窗口样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### hotkeyObject.modifyStyleEx(remove,add,swpFlags)

修改窗口扩展样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS\_EX_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS\_EX_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### hotkeyObject.postMessage(msg,wParam,lParam)

投递窗口消息到消息队列�?
此函数用法请参�?::User32.PostMessage

### hotkeyObject.redraw()

刷新

### hotkeyObject.reghotkey

```aardio aardio
hotkeyObject.reghotkey(
    function(id,mod,vk){
        /*输入响应热键的执行代�?/
    }
)

```

### hotkeyObject.right

右侧坐标

### hotkeyObject.sendMessage(msg,wParam,lParam)

发送窗口消�?
此函数用法请参�?::User32.SendMessage

### hotkeyObject.setFocus()

设置焦点

### hotkeyObject.setFont(指定字体)

指定LOGFONT字体对象,或逻辑字体句柄

### hotkeyObject.setFont(混入字体属�?

```aardio aardio
hotkeyObject.setFont(point=10;name="宋体");

```

### hotkeyObject.setParent(控件对象)

改变父窗�?
### hotkeyObject.setPos(x坐标,y坐标,�?�?插入位置,参数)

调整窗口位置或排�?所有参数可�?
同时指定x,y坐标则移动位�?
同时指定宽高则改变大�?
指定插入位置(句柄或\_HWND前缀常量)则调整Z�?
### hotkeyObject.setRect(rc)

设置控件区块位置(::RECT结构�?

### hotkeyObject.setRect(rc,true)

设置控件屏幕区块位置(::RECT结构�?

### hotkeyObject.show(true)

显示控件

### hotkeyObject.text

表示控件热键的文本，

使用此属性前必须导入标准�?key �?
注意 Ctrl,Alt,Shift 必须大写首字母小写其他字母，

键与键之间用 \+ 号分隔，忽略空格�?
无热键用空字符串表示�?
### hotkeyObject.theme

外观主题,例如

winform.button.theme = "Explorer"

winform.button.theme = false

### hotkeyObject.top

顶部坐标

### hotkeyObject.update()

重绘invalidate函数指定的区�?
### hotkeyObject.value

用于获取或设置设置，值为表示热键的数组�?
数组�?1 个成员为表示控制键的代码,

例如 \_MOD\_CONTROL,\_MOD\_ALT,\_MOD\_SHIFT 等�?
数组�?2 个成员为其他按键的虚拟键�?
### hotkeyObject.width

宽度

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/win/ui/ctrl/hotkey.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/win/ui/ctrl/hotkey.md')

