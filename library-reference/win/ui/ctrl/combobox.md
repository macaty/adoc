[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# win.ui.ctrl.combobox 库模块帮助文�?
## win.ui.ctrl 成员列表

### win.ui.ctrl.combobox()

下拉框控�?
[返回对象:comboboxObject](#comboboxObject)

## comboboxObject 成员列表

### comboboxObject.\_defWindowProc(hwnd,message,wParam,lParam)

用于�?wndproc 回调中提前调用默认消息回调函�?

所有窗口和控件定义�?wndproc 回调以后会自动创建这个函�?

调用此函数以�?wndproc 必须指定�?null 返回�?

以避免再次重复调用默认回调函�?
### comboboxObject.\_parentForm

控件所在的父窗�?指win.form对象)

[返回对象:winform](../_.html#winform)

### comboboxObject.add("文本")

添加到组合框,

支持0x100/\*\_CBS\_SORT\*/排序

### comboboxObject.autoComplete

用于onEditChange事件内部显示自动完成列表

此函数会在显示列表后保持输入文本与光标不�?
仅适用于dropdown模式

### comboboxObject.autoComplete(items,selIndex)

```aardio aardio
items参数使用一个字符串数组指定要显示的列表项，
@selIndex指定选项索引,不指定时默认�?

```

### comboboxObject.bottom

底部坐标

### comboboxObject.capture

是否捕获全局鼠标消息

### comboboxObject.className

运行时类�?
### comboboxObject.clear()

清除组合框所有内�?
### comboboxObject.close()

关闭控件窗口

### comboboxObject.cls

设计时类�?
### comboboxObject.count

列表项数�?
### comboboxObject.delete()

删除当前选中�?
### comboboxObject.dir("目录路径",\_DDL\_...)

类似dir命令,列出指定目录下匹配的文件,支持通配�?
参数@2可指定选项,默认�?\_DDL\_READWRITE

### comboboxObject.disabled

是否禁用

### comboboxObject.editBox

返回下拉控件编辑�?
[返回对象:editObject](edit.html#editObject)

### comboboxObject.find(请输入文�?

查找列表�?
### comboboxObject.findEx(请输入文�?

精确查找指定的项

找不到返�?

### comboboxObject.getClientRect()

控件客户区块位置(::RECT结构�?

[返回对象:rectObject](../../../global/_.html#rectObject)

### comboboxObject.getFont()

控件字体(::LOGFONT结构�?

[返回对象:logfontObject](#logfontObject)

### comboboxObject.getParent()

返回父窗�?
[返回对象:staticObject](static.html#staticObject)

### comboboxObject.getPos()

返回相对坐标,�?�?
x,y,cx,cy=win.getPos(hwnd)

### comboboxObject.getRect()

控件区块位置(::RECT结构�?

### comboboxObject.getRect(true)

控件屏幕区块位置(::RECT结构�?

### comboboxObject.height

高度

### comboboxObject.hide

控件是否隐藏

### comboboxObject.hwnd

控件句柄

### comboboxObject.id

控件ID

### comboboxObject.info()

返回COMBOBOXINFO结构�?

关于此结构体请查阅MSDN

### comboboxObject.insert("文本",插入位置)

默认添加到开始处,

-1表示添加到尾�?
不支�?x100/\*\_CBS\_SORT\*/排序

### comboboxObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/)

使窗口绘图区无效

### comboboxObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/,0)

使窗口绘图区无效

不刷新背�?
### comboboxObject.items

获取或设置组合框列表，属性值为字符串数组，

仅在属性面板设置初始化items属性时初始化selIndex�?�?
代码中动态修改items后请自行指定selIndex�?
如果自动指定了你不想要的selIndex，这会增加不必要的重绘�?
### comboboxObject.left

左侧坐标

### comboboxObject.limit

只写属�?修改最大允许输入的文本长度,

如果设为0,则设定为默认长度0x7FFFFFFE,

必须在控件初始化属性中启用横向滚动�?该属性才能生�?
### comboboxObject.listBox

返回下拉控件列表�?
[返回对象:listboxObject](#listboxObject)

### comboboxObject.minVisible

设置或获取下拉列表最小显示项目数�?
请在设计属性中启用垂直滚动条�?
如果不想多点一下，可如下改进此属性源码：

util.metaProperty.extend(win.ui.ctrl.combobox,{

minVisible = {

\_set = function( v ){

::SendMessageInt(owner.hwnd , 0x1701/\*\_CB\_SETMINVISIBLE\*/,v,0);

}

}

})

### comboboxObject.modifyStyle(remove,add,swpFlags)

修改窗口样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### comboboxObject.modifyStyleEx(remove,add,swpFlags)

修改窗口扩展样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS\_EX_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS\_EX_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### comboboxObject.onCancel()

```aardio aardio
comboboxObject.onCancel = function(){
    /*响应事件，用户未确认选项且且下拉框即将关�?例如用户点击其他控件关闭下拉列表或直接关闭窗�?/
}

```

### comboboxObject.onCloseUp()

```aardio aardio
comboboxObject.onCloseUp = function(){
    /*下拉列表隐藏时触发此事件*/
}

```

### comboboxObject.onDropDown()

```aardio aardio
comboboxObject.onDropDown = function(){
    /*弹出下拉列表前触发此事件
用代码调�?showDropDown 函数也会触发此事�?/
}

```

### comboboxObject.onEditChange()

```aardio aardio
comboboxObject.onEditChange = function(){
    /*响应事件，输入框中的文本已变�?
只有用户输入时才会触�?
切换选项或使用代码修改text属性不会触�?注意使用text属性取最新�?/
}

```

### comboboxObject.onFocusGot()

```aardio aardio
comboboxObject.onFocusGot = function(){
    /*下拉框获得焦点时触发此事�?/
}

```

### comboboxObject.onFocusLost()

```aardio aardio
comboboxObject.onFocusLost = function(){
    /*下拉框失去焦点时触发此事�?/
}

```

### comboboxObject.onListChange()

```aardio aardio
comboboxObject.onListChange = function(){
    /*改变当前选项触发此事件�?在下拉框上按方向键调整当前选项会触发此事件�?在选项上回车确认选项时，如果选项已改变则会触发此事件�?如果回车操作未改变选项仅触�?onOk 事件�?
注意事件中要�?selText 属性取新的�?使用代码修改 selIndex 是不会触�?/
}

```

### comboboxObject.onOk()

```aardio aardio
comboboxObject.onOk = function(){
    /*响应事件，用户已确认选择指定选项,
注意事件中要�?selText 属性取新的�?单击选项或在选项上回车都会触发此事件（无论是否改变选项�?/
}

```

### comboboxObject.oncommand(id,event)

```aardio aardio
comboboxObject.oncommand = function(id,event){
    var text = owner.selText;
    /*响应事件，event比较常用的值：
_CBN_SELCHANGE表示正在改变当前�?但下拉框还没有关�?_CBN_SELENDOK表示已改变选项且下拉框即将关闭
注意事件中要用selText属性取新的�?/
}

```

### comboboxObject.orphanWindow(transparent,hwndBuddy)

创建悬浮窗口,

悬浮窗口仍然显示在原来的位置,

悬浮窗口如影随形的跟随父窗口移动或改变大�?控件原来的固定边距等参数仍然有效

此控件不建议指定参数

### comboboxObject.postMessage(msg,wParam,lParam)

投递窗口消息到消息队列�?
此函数用法请参�?::User32.PostMessage

### comboboxObject.redraw()

刷新

### comboboxObject.right

右侧坐标

### comboboxObject.selIndex

获取或指定当前选中的项索引,属性值为数�?

设为null取消选项

### comboboxObject.selText

读取或设置组合框当前选中文本

在onOk事件回调中获取最新值应当使用selText而不是text属�?
获取或指定当前选中的文�?精确匹配

### comboboxObject.selectString("文本前缀",开始索�?

按文本前缀查找并选中项目,

自开始索引后面开始查�?默认值为0也就是开始处搜索

### comboboxObject.sendMessage(msg,wParam,lParam)

发送窗口消�?
此函数用法请参�?::User32.SendMessage

### comboboxObject.setCueBannerText("提示文本")

指定文本框文本为空时的显示的默认提示文本,

此函数会取消当前选中�?

XP系统不支持此函数、但调用不报�?
### comboboxObject.setCueBannerText(提示文本)

设置文本为空的输入提示，

参数 @1 使用字符串指定提示内容�?
此函数会自动设置控件 text 属性为�?
### comboboxObject.setFocus()

设置焦点

### comboboxObject.setFont(指定字体)

指定LOGFONT字体对象,或逻辑字体句柄

### comboboxObject.setFont(混入字体属�?

```aardio aardio
comboboxObject.setFont(point=10;name="宋体");

```

### comboboxObject.setParent(控件对象)

改变父窗�?
### comboboxObject.setPos(x坐标,y坐标,�?�?插入位置,参数)

调整窗口位置或排�?所有参数可�?
同时指定x,y坐标则移动位�?
同时指定宽高则改变大�?
指定插入位置(句柄或\_HWND前缀常量)则调整Z�?
### comboboxObject.setRect(rc)

设置控件区块位置(::RECT结构�?

### comboboxObject.setRect(rc,true)

设置控件屏幕区块位置(::RECT结构�?

### comboboxObject.show(true)

显示控件

### comboboxObject.showDropDown(true)

显示下拉列表

参数为false隐藏下拉列表

### comboboxObject.tabNext()

[返回对象:staticObject](static.html#staticObject)

### comboboxObject.tabNext(移动焦点,是否反向)

获取下一个支持tab控制焦点的控�?
参数@1为true会自动移动焦点到该控�?
参数@2为true则获取上一个控�?否则获取下一个控�?
### comboboxObject.text

组合框当前输入文�?
在onOk事件回调中获取最新值应当使用selText而不是text属�?
### comboboxObject.theme

外观主题,例如

winform.button.theme = "Explorer"

winform.button.theme = false

### comboboxObject.threadCallable()

开启此控件的跨线程调用功能

### comboboxObject.top

顶部坐标

### comboboxObject.topIndex

获取此属性返回首个可见项索引�?
设置此属性为项目索引则滚动到该项可见�?
项目起始索引�?1

### comboboxObject.update()

重绘invalidate函数指定的区�?
### comboboxObject.valid

窗口是否有效�?
窗口未关闭返�?true �?
窗口已关闭或正在关闭返回 false

### comboboxObject.width

宽度

### 自动完成常量

\_CBN\_CLOSEUP=8

\_CBN\_DBLCLK=2

\_CBN\_DROPDOWN=7

\_CBN\_EDITCHANGE=5

\_CBN\_EDITUPDATE=6

\_CBN\_KILLFOCUS=4

\_CBN\_SELCHANGE=1

\_CBN\_SELENDCANCEL=0xA

\_CBN\_SELENDOK=9

\_CBN\_SETFOCUS=3

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/win/ui/ctrl/combobox.md)

