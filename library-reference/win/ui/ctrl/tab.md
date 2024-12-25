[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# win.ui.ctrl.tab 库模块帮助文�?
[简单选项卡使用指南](https://www.aardio.com/zh-cn/doc/library-guide/std/win/ui/ctrl/tab.md)

## win.ui.ctrl 成员列表

### win.ui.ctrl.tab()

简单选项卡控件（ classic tab control �?
[返回对象:uiTabObject](#uiTabObject)

## uiTabObject 成员列表

### uiTabObject.\_parentForm

创建该控件的父窗口（win.form对象�?

设计时窗体容器是所有拖放在窗体上的控件�?\_parentForm,

即使窗口移除子窗口样式、更改父子关系，或以 orphanWindow显示,

控件�?\_parentForm 始终都不会改�?
[返回对象:winform](../_.html#winform)

### uiTabObject.add()

创建选项卡（同时创建选项卡按钮与显示内容的子窗口），返回子窗口（win.form 对象）�?
参数 @1 指定一个表参数，与 win.form 对象的构造参数相同�?
可在窗体设计器中复制 win.form 对象的构造参数作为此函数的参数�?
表参数中�?text 字段指定表示选项卡标题（也即子窗口标题）�?
参数 @1 也可以用字符串指定创建子窗口的代码文件路径�?
[返回对象:winform](../_.html#winform)

### uiTabObject.adjust

```aardio aardio
uiTabObject.adjust = function( cx,cy,wParam ) {
    /*窗口缩放时会自动触发此函数�?cx 参数为窗口宽�?cy 参数为窗口高�?
wParam 参数请参�?_WM_SIZE 消息参数说明,一般不用管�?
所�?win.form 创建的窗体和控件都支持此事件,
重复赋值只会追加而不会覆盖此事件�?一般不建议添加一�?wndproc 仅仅是为了处�? _WM_SIZE 消息�?定义 adjust 事件是更好的选择�?
可主动调用此事件,省略参数�?cx,cy 参数默认设为窗口大小*/
};

```

### uiTabObject.adjustRect()

调整子窗口大小以适应客户�?
### uiTabObject.bottom

底部坐标

### uiTabObject.capture

是否捕获全局鼠标消息

### uiTabObject.className

运行时类�?
### uiTabObject.close()

关闭控件窗口

### uiTabObject.cls

设计时类�?
### uiTabObject.disabled

是否禁用

### uiTabObject.form

[返回对象:winform](../_.html#winform)

### uiTabObject.getClientRect()

控件客户区块位置(::RECT结构�?

[返回对象:rectObject](../../../global/_.html#rectObject)

### uiTabObject.getFont()

控件字体(::LOGFONT结构�?

[返回对象:logfontObject](#logfontObject)

### uiTabObject.getItem(索引)

读取选项结构�?
### uiTabObject.getItemRect(索引)

读取选项卡区块位�?
### uiTabObject.getItemText(索引)

读取选项卡标�?
### uiTabObject.getParent()

返回父窗�?
[返回对象:staticObject](static.html#staticObject)

### uiTabObject.getPos()

返回相对坐标,�?�?
x,y,cx,cy=win.getPos(hwnd)

### uiTabObject.getRect()

控件区块位置(::RECT结构�?

### uiTabObject.getRect(true)

控件屏幕区块位置(::RECT结构�?

### uiTabObject.height

高度

### uiTabObject.hitTest(x坐标,y坐标,是否屏幕坐标)

返回坐标指向的选项索引

参数三可省略,默认为false.

如果不指定任何参�?则自动调�?win.getMessagePos() 获取消息坐标

### uiTabObject.hwnd

控件句柄

### uiTabObject.id

控件ID

### uiTabObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/)

使窗口绘图区无效

### uiTabObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/,0)

使窗口绘图区无效

不刷新背�?
### uiTabObject.items

返回子窗口列�?只读属�?
### uiTabObject.items.?

选项卡子窗口

[返回对象:winform](../_.html#winform)

### uiTabObject.left

左侧坐标

### uiTabObject.loadForm

加载并添加显示内容的子窗口到选项卡控件�?
返回加载到选项卡的子窗体（ win.form 对象）�?
### uiTabObject.loadForm(codePath)

加载并添加显示内容的子窗口到选项卡控件�?
返回加载到选项卡的子窗体（ win.form 对象）�?
参数 @codePath 指定创建窗体的代码文件路径�?
请注意保存外部窗体文件以后测试运行�?
### uiTabObject.loadForm(tParam)

使用表参�?@tParam 创建显示内容的子窗口并添加到选项卡控件�?
返回加载到选项卡的子窗体（ win.form 对象）�?
参数 @tParam 用法�?win.form 构造参数相同�?
### uiTabObject.modifyStyle(remove,add,swpFlags)

修改窗口样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### uiTabObject.modifyStyleEx(remove,add,swpFlags)

修改窗口扩展样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS\_EX_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS\_EX_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### uiTabObject.onDestroy

```aardio aardio
uiTabObject.onDestroy = function(){
    /*窗口销毁前触发*/
}

```

### uiTabObject.onDrawItem

```aardio aardio
uiTabObject.onDrawItem = function(drawItem){
    if( drawItem.CtlType == 101 /*_ODT_TAB*/ ){
        /*自绘选项�?创建控件的参数中需要添加ownerDraw=true*/
    }
}

```

### uiTabObject.onSelchange

```aardio aardio
uiTabObject.onSelchange = function(idx,form){
    /*切找选项卡触发此事件�?idx 为当前选项索引，数值�?form 为当前选项页，等价�?tab 控件�?form 属性�?/
}

```

### uiTabObject.oncommand

```aardio aardio
uiTabObject.oncommand = function(id,event){
    /*命令事件触发*/
}

```

### uiTabObject.onnotify

```aardio aardio
uiTabObject.onnotify = function(id,code,ptr){
    /*通知事件触发*/
}

```

### uiTabObject.postMessage(msg,wParam,lParam)

投递窗口消息到消息队列�?
此函数用法请参�?::User32.PostMessage

### uiTabObject.redraw()

刷新

### uiTabObject.remove()

参数为数�?移除指定索引的选项�?
### uiTabObject.removeAll()

移除所有选项�?
### uiTabObject.right

右侧坐标

### uiTabObject.selIndex

读取或设置当前选项索引

起始索引�?

### uiTabObject.sendMessage(msg,wParam,lParam)

发送窗口消�?
此函数用法请参�?::User32.SendMessage

### uiTabObject.setFocus()

设置焦点

### uiTabObject.setFont(指定字体)

指定LOGFONT字体对象,或逻辑字体句柄

### uiTabObject.setFont(混入字体属�?

```aardio aardio
uiTabObject.setFont(point=10;name="宋体");

```

### uiTabObject.setItem(索引,"字符串参�?)

设置选项结构�?
### uiTabObject.setItemText(索引,"字符串参�?)

设置选项卡标�?
### uiTabObject.setParent(控件对象)

改变父窗�?
### uiTabObject.setPos(x坐标,y坐标,�?�?插入位置,参数)

调整窗口位置或排�?所有参数可�?
同时指定x,y坐标则移动位�?
同时指定宽高则改变大�?
指定插入位置(句柄或\_HWND前缀常量)则调整Z�?
### uiTabObject.setRect(rc)

设置控件区块位置(::RECT结构�?

### uiTabObject.setRect(rc,true)

设置控件屏幕区块位置(::RECT结构�?

### uiTabObject.setRedraw(false)

禁止重绘

### uiTabObject.setRedraw(true)

恢复重绘

### uiTabObject.show(true)

显示控件

### uiTabObject.theme

外观主题,例如

winform.button.theme = "Explorer"

winform.button.theme = false

### uiTabObject.threadCallable()

开启此控件的跨线程调用功能

### uiTabObject.top

顶部坐标

### uiTabObject.update()

重绘invalidate函数指定的区�?
### uiTabObject.width

宽度

### uiTabObject.wndproc

```aardio aardio
uiTabObject.wndproc = function(hwnd,message,wParam,lParam){
    /*窗口消息回调，返回任意非null值阻止默认回�?wndproc重复赋值时追加函数而不是覆盖之前的回调
设为null添除所有消息回调函�?wndproc也可以是一个表,键要为处理的消息,值为对应的消息回调函�?/
}

```

## win.ui.ctrl.tab 成员列表

### win.ui.ctrl.tab.TCITEM()

选项结构�?
### 自动完成常量

\_TCM\_FIRST=0x1300

\_TCS\_BOTTOM=2

\_TCS\_BUTTONS=0x100

\_TCS\_FIXEDWIDTH=0x400

\_TCS\_FLATBUTTONS=8

\_TCS\_FOCUSNEVER=0x8000

\_TCS\_FOCUSONBUTTONDOWN=0x1000

\_TCS\_FORCEICONLEFT=0x10

\_TCS\_FORCELABELLEFT=0x20

\_TCS\_HOTTRACK=0x40

\_TCS\_MULTILINE=0x200

\_TCS\_MULTISELECT=4

\_TCS\_OWNERDRAWFIXED=0x2000

\_TCS\_RAGGEDRIGHT=0x800

\_TCS\_RIGHT=2

\_TCS\_RIGHTJUSTIFY=0

\_TCS\_SCROLLOPPOSITE=1

\_TCS\_SINGLELINE=0

\_TCS\_TABS=0

\_TCS\_TOOLTIPS=0x4000

\_TCS\_VERTICAL=0x80

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/win/ui/ctrl/tab.md)

