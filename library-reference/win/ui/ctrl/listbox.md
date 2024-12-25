[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# win.ui.ctrl.listbox 库模块帮助文�?
## win.ui.ctrl 成员列表

### win.ui.ctrl.listbox()

列表�?
listbox 默认会自动调整高度以对齐项目行高,

在创建参数中添加 integralHeight = false 可禁止此特�?
[返回对象:listboxObject](#listboxObject)

## listboxObject 成员列表

### listboxObject.\_defWindowProc(hwnd,message,wParam,lParam)

用于�?wndproc 回调中提前调用默认消息回调函�?

所有窗口和控件定义�?wndproc 回调以后会自动创建这个函�?

调用此函数以�?wndproc 必须指定�?null 返回�?

以避免再次重复调用默认回调函�?
### listboxObject.\_parentForm

创建该控件的父窗口（win.form对象�?

设计时窗体容器是所有拖放在窗体上的控件�?\_parentForm,

即使窗口移除子窗口样式、更改父子关系，或以 orphanWindow显示,

控件�?\_parentForm 始终都不会改�?
[返回对象:winform](../_.html#winform)

### listboxObject.add(请输入文�?

添加列表项到尾部，返回新项目索引�?
### listboxObject.add(请输入文�?-1)

添加列表项到尾部，返回新项目索引�?
### listboxObject.add(请输入文�?1)

添加列表项到头部，返回新项目索引�?
### listboxObject.addCtrl

```aardio aardio
listboxObject.addCtrl(

    edit ={ cls="edit";left=0;top=0;right=50;bottom=50;autoResize=false ;hide=1;edge=1;  }
)

```

### listboxObject.addfile(请输入路�?

向列表框里增加一个文�?包括目录)

### listboxObject.adjust

```aardio aardio
listboxObject.adjust = function( cx,cy,wParam ) {
    /*窗口缩放时会自动触发此函数�?cx 参数为窗口宽�?cy 参数为窗口高�?
wParam 参数请参�?_WM_SIZE 消息参数说明,一般不用管�?
所�?win.form 创建的窗体和控件都支持此事件,
重复赋值只会追加而不会覆盖此事件�?一般不建议添加一�?wndproc 仅仅是为了处�? _WM_SIZE 消息�?定义 adjust 事件是更好的选择�?
可主动调用此事件,省略参数�?cx,cy 参数默认设为窗口大小*/
};

```

### listboxObject.bottom

底部坐标

注意listbox的实际高度受行高的影�?
只有自绘时才能设置行�?
### listboxObject.capture

是否捕获全局鼠标消息

### listboxObject.className

运行时类�?
### listboxObject.clear()

清除列表框所有内�?
### listboxObject.clientRect

获取控件客户区块位置(::RECT结构�?

### listboxObject.close()

关闭控件�?
### listboxObject.cls

设计时类�?
### listboxObject.count

列表项数�?
### listboxObject.delete()

删除当前选中�?
删除指定�?
### listboxObject.disabled

是否禁用

### listboxObject.eachSelected()

```aardio aardio
for index,text in listboxObject.eachSelected(){
    /*从后向前倒序遍历所有选中�?
迭代变量 index 为选中项序�?
迭代变量 text 当前行文本�?/
}

```

### listboxObject.ensureVisible()

滚动视图以确定可以显示参数指定行序号的项,

不指定参数则设置当前选中焦点�?
### listboxObject.find(请输入文�?

在列表框里查找指定的�?
找不到返�?

### listboxObject.findEx(请输入文�?

精确查找指定的项

找不到返�?

### listboxObject.getClientRect()

控件客户区块位置(::RECT结构�?

[返回对象:rectObject](../../../global/_.html#rectObject)

### listboxObject.getFont()

控件字体(::LOGFONT结构�?

[返回对象:logfontObject](#logfontObject)

### listboxObject.getItemRect(项索�?

获取指定项区块位�?
返回::RECT() 结构�?
### listboxObject.getItemText(项索�?

获取指定项文�?
### listboxObject.getParent()

返回父窗�?
[返回对象:staticObject](static.html#staticObject)

### listboxObject.getPos()

返回相对坐标,�?�?
x,y,cx,cy=win.getPos(hwnd)

### listboxObject.getRect()

控件区块位置(::RECT结构�?

### listboxObject.getRect(true)

控件屏幕区块位置(::RECT结构�?

### listboxObject.getSelected(1项索�?

是否选中

### listboxObject.height

高度

listbox 默认会自动调整高度以对齐项目行高,

在创建参数中添加 integralHeight = false 可禁止此特�?
### listboxObject.hitTest(x,y)

返回指定客户区坐标所在的项索�?

### listboxObject.hitTest(x坐标,y坐标,是否屏幕坐标)

该函数返回指定坐标的句柄,参数三可省略,默认为false.

如果不指定任何参�?则自动获取当前消息坐�?
### listboxObject.hwnd

控件句柄

### listboxObject.id

控件ID

### listboxObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/)

使窗口绘图区无效

### listboxObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/,0)

使窗口绘图区无效

不刷新背�?
### listboxObject.items

列表项集�?
table对象

### listboxObject.left

左侧坐标

### listboxObject.modifyStyle(remove,add,swpFlags)

修改窗口样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### listboxObject.modifyStyleEx(remove,add,swpFlags)

修改窗口扩展样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS\_EX_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS\_EX_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### listboxObject.onDestroy

```aardio aardio
listboxObject.onDestroy = function(){
    /*窗口销毁前触发*/
}

```

### listboxObject.onDoubleClickItem()

```aardio aardio
listboxObject.onDoubleClickItem = function(){
    /*双击列表项触发此事件,
使使�?selIndex 获取双击的项*/
}

```

### listboxObject.onDrawItem(drawItem)

```aardio aardio
listboxObject.onDrawItem = function(drawItem){
    /*控件属性里指定 ownerDraw �?true 触发此事�?在这里自绘控件项*/
}

```

### listboxObject.onKillFocus()

```aardio aardio
listboxObject.onKillFocus = function(){
    /*失去焦点触发此事�?/
}

```

### listboxObject.onMeasureItem(measureItem,dpiScaleX,dpiScaleY)

```aardio aardio
listboxObject.onMeasureItem = function(measureItem){
    measureItem.itemHeight = 61 * dpiScaleY;
    /*控件属性里指定 ownerDraw �?true 触发此事�?在这里配置自绘控件项参数*/
}

```

### listboxObject.onSelCancel()

```aardio aardio
listboxObject.onSelCancel = function(){
    /*取消选项时触发此事件*/
}

```

### listboxObject.onSelChange()

```aardio aardio
listboxObject.onSelChange = function(){
    /*改变当前选项时触发此事件*/
}

```

### listboxObject.onSetFocus()

```aardio aardio
listboxObject.onSetFocus = function(){
    /*获得焦点触发此事�?/
}

```

### listboxObject.oncommand

```aardio aardio
listboxObject.oncommand = function(id,event){
    /*命令事件触发*/
}

```

### listboxObject.onnotify

```aardio aardio
listboxObject.onnotify = function(id,code,ptr){
    /*通知事件触发*/
}

```

### listboxObject.orphanWindow(transparent,hwndBuddy,borderless)

创建悬浮窗口�?
悬浮窗口是模仿子窗口外观效果的独立窗口，父窗口可自动调整子窗口到设定位置�?
可选参�?@transparent �?true 则转换为分层透明窗口�?
可选利�?@hwndBuddy 参数指定外部进程窗口句柄的并附加在内部控件上以实现相同的效果�?
伙伴窗口总是会保持在悬浮窗口前面，并保持相同的大小、位置�?
可重复调用此函数更换伙伴窗口，旧的伙伴窗口必须自行关闭�?
可选指�?@borderless 参数 �?true 以移�?@hwndBuddy 的窗口边框�?
### listboxObject.postMessage(msg,wParam,lParam)

投递窗口消息到消息队列�?
此函数用法请参�?::User32.PostMessage

### listboxObject.redraw()

刷新

### listboxObject.right

右侧坐标

### listboxObject.selIndex

获取或设置列表框当前选中�?
仅在单选模式下有效,多选模式下请使�?selected 获取所有获中项

### listboxObject.selText

获取当前选项的文�?
或根据指定的文本查找并改变选项

### listboxObject.selectRange(1,)

选中指定范围

如果不指定任何参�?取消选区

### listboxObject.selected

所有选中项目索引的数�?

设为 null 或空表清除所有选中�?
### listboxObject.sendMessage(msg,wParam,lParam)

发送窗口消�?
此函数用法请参�?::User32.SendMessage

### listboxObject.setFocus()

设置焦点

### listboxObject.setFont(指定字体)

指定LOGFONT字体对象,或逻辑字体句柄

### listboxObject.setFont(混入字体属�?

```aardio aardio
listboxObject.setFont(point=10;name="宋体");

```

### listboxObject.setParent(控件对象)

改变父窗�?
### listboxObject.setPos(x坐标,y坐标,�?�?插入位置,参数)

调整窗口位置或排�?所有参数可�?
同时指定x,y坐标则移动位置，同时指定宽高则改变大小，

指定插入位置（句柄或\_HWND前缀常量）则调整Z�?
listbox 默认会自动调整高度以对齐项目行高,

在创建参数中添加 integralHeight = false 可禁止此特�?
### listboxObject.setRect(rc)

设置控件区块位置(::RECT结构�?

### listboxObject.setRect(rc,true)

设置控件屏幕区块位置(::RECT结构�?

### listboxObject.setSelected(1项索�?

选中指定�?索引�?则选定全部

该函数仅在开启控件多选模式下有效

单选模式下请使用selIndex属性替�?
### listboxObject.setSelected(1项索�?false)

取消选中指定�?索引�?则取消全�?
### listboxObject.show(true)

显示控件

### listboxObject.theme

外观主题,例如

winform.button.theme = "Explorer"

winform.button.theme = false

### listboxObject.threadCallable()

开启此控件的跨线程调用功能

### listboxObject.top

顶部坐标

### listboxObject.update()

重绘invalidate函数指定的区�?
### listboxObject.width

宽度

### listboxObject.wndproc

```aardio aardio
listboxObject.wndproc = function(hwnd,message,wParam,lParam){
    /*窗口消息回调，返回任意非null值阻止默认回�?wndproc重复赋值时追加函数而不是覆盖之前的回调
设为null添除所有消息回调函�?wndproc也可以是一个表,键要为处理的消息,值为对应的消息回调函�?/
}

```

### 自动完成常量

\_LBN\_DBLCLK=0x2

\_LBN\_KILLFOCUS=0x5

\_LBN\_SELCANCEL=0x3

\_LBN\_SELCHANGE=0x1

\_LBN\_SETFOCUS=0x4

\_LBS\_DISABLENOSCROLL=0x1000

\_LBS\_EXTENDEDSEL=0x800

\_LBS\_HASSTRINGS=0x40

\_LBS\_MULTICOLUMN=0x200

\_LBS\_MULTIPLESEL=0x8

\_LBS\_NODATA=0x2000

\_LBS\_NOINTEGRALHEIGHT=0x100

\_LBS\_NOREDRAW=0x4

\_LBS\_NOTIFY=0x1

\_LBS\_OWNERDRAWFIXED=0x10

\_LBS\_OWNERDRAWVARIABLE=0x20

\_LBS\_SORT=0x2

\_LBS\_USETABSTOPS=0x80

\_LBS\_WANTKEYBOARDINPUT=0x400

\_LB\_ADDFILE=0x196

\_LB\_ADDSTRING=0x180

\_LB\_CTLCODE=0x0

\_LB\_DELETESTRING=0x182

\_LB\_DIR=0x18D

\_LB\_FINDSTRING=0x18F

\_LB\_FINDSTRINGEXACT=0x1A2

\_LB\_GETANCHORINDEX=0x19D

\_LB\_GETCARETINDEX=0x19F

\_LB\_GETCOUNT=0x18B

\_LB\_GETCURSEL=0x188

\_LB\_GETHORIZONTALEXTENT=0x193

\_LB\_GETITEMDATA=0x199

\_LB\_GETITEMHEIGHT=0x1A1

\_LB\_GETITEMRECT=0x198

\_LB\_GETLOCALE=0x1A6

\_LB\_GETSEL=0x187

\_LB\_GETSELCOUNT=0x190

\_LB\_GETSELITEMS=0x191

\_LB\_GETTEXT=0x189

\_LB\_GETTEXTLEN=0x18A

\_LB\_GETTOPINDEX=0x18E

\_LB\_INSERTSTRING=0x181

\_LB\_MSGMAX=0x1A8

\_LB\_OKAY=0x0

\_LB\_RESETCONTENT=0x184

\_LB\_SELECTSTRING=0x18C

\_LB\_SELITEMRANGE=0x19B

\_LB\_SELITEMRANGEEX=0x183

\_LB\_SETANCHORINDEX=0x19C

\_LB\_SETCARETINDEX=0x19E

\_LB\_SETCOLUMNWIDTH=0x195

\_LB\_SETCOUNT=0x1A7

\_LB\_SETCURSEL=0x186

\_LB\_SETHORIZONTALEXTENT=0x194

\_LB\_SETITEMDATA=0x19A

\_LB\_SETITEMHEIGHT=0x1A0

\_LB\_SETLOCALE=0x1A5

\_LB\_SETSEL=0x185

\_LB\_SETTABSTOPS=0x192

\_LB\_SETTOPINDEX=0x197

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/win/ui/ctrl/listbox.md)

