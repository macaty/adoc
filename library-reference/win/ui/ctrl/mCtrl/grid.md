[aardio 文档](../../../../../index.htm "aardio 编程语言文档首页")

# win.ui.ctrl.mCtrl.grid 库模块帮助文�?
## mCtrlGridGeometryObject 成员列表

### mCtrlGridGeometryObject.columnHeaderHeight

列标题高�?
### mCtrlGridGeometryObject.defColumnWidth

默认列宽

### mCtrlGridGeometryObject.defRowHeight

默认行高

### mCtrlGridGeometryObject.paddingHorz

水平边距

### mCtrlGridGeometryObject.paddingVert

垂直边距

### mCtrlGridGeometryObject.rowHeaderWidth

行标题宽�?
### mCtrlGridGeometryObject.update()

更新

## mCtrlGridObject 成员列表

### mCtrlGridObject.\_embedObject

嵌入OLE控件对象

[返回对象:embedObject](../../../../com/_.html#embedObject)

### mCtrlGridObject.\_parentForm

控件所在的父窗�?指win.form对象)

[返回对象:winform](../../_.html#winform)

### mCtrlGridObject.addCtrl

```aardio aardio
mCtrlGridObject.addCtrl(
    button={ cls="button";text="button";left=33;top=32;right=126;bottom=81;autoResize=false }
)

```

### mCtrlGridObject.adjust

```aardio aardio
mCtrlGridObject.adjust = function( cx,cy,wParam ) {

};

```

### mCtrlGridObject.adjust()

调整窗口 \- 自定义事件函�?
### mCtrlGridObject.bgcolor

获取或修改景颜色数�?
### mCtrlGridObject.bottom

底部坐标

### mCtrlGridObject.capture

是否捕获全局鼠标消息

### mCtrlGridObject.changeInterval(定时器ID,间隔时间,回调函数)

重新设置间隔时间或回调函�?
### mCtrlGridObject.className

运行时类�?
### mCtrlGridObject.clear(行总数,列总数)

清空表格,

不指定清空全部内�?
\| 1 清空普通单元格,

\| 2 清空列标�?
\| 4 清空行标�?
### mCtrlGridObject.clearInterval(定时器ID)

删除定时�?
参数如果为null则忽略不执行

否则定时器ID必须是setInterval函数或setTimeout函数的返回�?
### mCtrlGridObject.close()

关闭控件窗口

### mCtrlGridObject.cls

设计时类�?
### mCtrlGridObject.color

获取或修改字体颜色数�?
### mCtrlGridObject.columnCount()

列总数

### mCtrlGridObject.createEmbed("类名",容器对象)

嵌入COM控件,

参数@1也可以指定一个已存在的COM对象,

容器对象为可选参�?返回容器对象

创建失败会抛出异�?
### mCtrlGridObject.createEmbed()

[返回对象:embedObject](../../../../com/_.html#embedObject)

### mCtrlGridObject.createTable()

创建并返�?win.ui.ctrl.mCtrl.gridTable对象

[返回对象:mCtrlGridTableObject](#mCtrlGridTableObject)

### mCtrlGridObject.disabled

是否禁用

### mCtrlGridObject.disabledText

指定文本�?禁用此控�?并显示指定文�?

指定为null�?启用此控�?并恢复控件之前的正常文本

### mCtrlGridObject.geometry()

返回外观设置结构体，可调用返回对象的 update 函数更新

[返回对象:mCtrlGridGeometryObject](#mCtrlGridGeometryObject)

### mCtrlGridObject.getCell(行号,列号)

返回指定列的MC\_TABLECELL结构�?
行号省略表示列标题，列号省略表示行标�?
### mCtrlGridObject.getCellTextl(行号,列号)

返回指定列的文本

行号省略表示列标题，列号省略表示行标�?
### mCtrlGridObject.getClientRect()

控件客户区块位置(::RECT结构�?

[返回对象:rectObject](../../../../global/_.html#rectObject)

### mCtrlGridObject.getEditor()

返回编辑�?
[返回对象:editObject](../edit.html#editObject)

### mCtrlGridObject.getFont()

控件字体(::LOGFONT结构�?

[返回对象:logfontObject](#logfontObject)

### mCtrlGridObject.getForm()

如果是窗体返回自�?
如果是控件则返回\_parentForm

[返回对象:winform](../../_.html#winform)

### mCtrlGridObject.getParent()

返回父窗�?
### mCtrlGridObject.getPos()

返回相对父窗口客户区的坐�?�?�?

参数为true返回屏幕坐标,�?�?

x,y,cx,cy=win.getPos(hwnd)

### mCtrlGridObject.getRect()

控件区块位置(::RECT结构�?

### mCtrlGridObject.getRect(true)

控件屏幕区块位置(::RECT结构�?

### mCtrlGridObject.getRowHeight(行号)

获取行高�?
### mCtrlGridObject.getSelection()

返回选区

### mCtrlGridObject.getTable()

返回控件绑定的数据表

[返回对象:mCtrlGridTableObject](#mCtrlGridTableObject)

### mCtrlGridObject.group()

将在此控件范围内的所有其他控件设为此控件的子窗口

### mCtrlGridObject.height

高度

### mCtrlGridObject.hide

控件是否隐藏

### mCtrlGridObject.hwnd

控件句柄

### mCtrlGridObject.id

控件ID

### mCtrlGridObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/)

使窗口绘图区无效

### mCtrlGridObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/,0)

使窗口绘图区无效

不刷新背�?
### mCtrlGridObject.isForm

窗体返回true,控件返回false

### mCtrlGridObject.left

左侧坐标

### mCtrlGridObject.messageOnly()

将窗口转换为message-only window

该窗口不可见,仅用于消息分�?
### mCtrlGridObject.modifyStyle(remove,add)

如果指定第三个参�?则使用此参数调用::SetWidnowPos

### mCtrlGridObject.modifyStyleEx(remove,add)

如果指定第三个参�?则使用此参数调用::SetWidnowPos

### mCtrlGridObject.msgErr()

显示错误提示�?
请先调用win.dlg.message.install安装此函�?
### mCtrlGridObject.msgFrown()

显示皱眉图标提示�?
请先调用win.dlg.message.install安装此函�?
### mCtrlGridObject.msgGreat()

显示竖大拇指图标提示�?
请先调用win.dlg.message.install安装此函�?
### mCtrlGridObject.msgInfo()

显示提示�?
请先调用win.dlg.message.install安装此函�?
### mCtrlGridObject.msgOk()

显示正确提示�?
请先调用win.dlg.message.install安装此函�?
### mCtrlGridObject.msgSmile()

显示微笑图标提示�?
请先调用win.dlg.message.install安装此函�?
### mCtrlGridObject.msgSorry()

显示倒竖大拇指图标提示框

请先调用win.dlg.message.install安装此函�?
### mCtrlGridObject.msgWarn()

显示警告提示�?
请先调用win.dlg.message.install安装此函�?
### mCtrlGridObject.msgbox("字符串参�?)

弹出对话�?可选用参数@2指定标题

### mCtrlGridObject.msgboxErr("字符串参�?)

弹出错误对话�?可选用参数@2指定标题

### mCtrlGridObject.msgboxTest("字符串参�?)

弹出询问对话�?可选用参数@2指定标题

### mCtrlGridObject.onDestroy

```aardio aardio
mCtrlGridObject.onDestroy = function(){
    /*窗口销毁前触发*/
}

```

### mCtrlGridObject.onEditChanged

```aardio aardio
mCtrlGridObject.onEditChanged = function(text,row,col,dispInfo){
    /*text为列文本,row为行�?col为列�?返回值指定是否允许更新列文本*/
    return true;
}

```

### mCtrlGridObject.oncommand

```aardio aardio
mCtrlGridObject.oncommand = function(id,event){
    /*命令事件触发*/
}

```

### mCtrlGridObject.onnotify

```aardio aardio
mCtrlGridObject.onnotify = function(id,code,ptr){
    /*通知事件触发*/
}

```

### mCtrlGridObject.orphanWindow()

使控件脱离原来的窗口,可以显示在父窗口外面,

但仍然显示在原来的位�?继续如影随形的跟随父窗口移动或改变大�?

控件原来的固定边距等参数仍然有效

### mCtrlGridObject.postMessage(msg,wParam,lParam)

投递窗口消息到消息队列�?
此函数用法请参�?::User32.PostMessage

### mCtrlGridObject.publish("字符串参�?,)

在窗口所在界面线程发布消�?

运行界面线程所有所有调用subscribe函数订阅此消息的函数,

可添加任意个触发参数

### mCtrlGridObject.redraw()

刷新

### mCtrlGridObject.redrawTransparent()

刷新

透明背景时请使用此函数替代redraw()

### mCtrlGridObject.reduce(array,callback,debounce)

```aardio aardio
mCtrlGridObject.reduce(
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

### mCtrlGridObject.reloadScale()

按设计时位置参数、重新调整控件位置以适应窗口当前缩放比例�?
父窗口缩放时会自动执行此操作�?
默认在启动窗口消息循环时会自适应调整所有控件�?
所以在启动消息循环前添加控件不必调用此函数�?
### mCtrlGridObject.resize

发送WM\_SIZE消息给窗�?
### mCtrlGridObject.resize(宽度,高度)

如果指定了参数则调整窗口大小,

无论是否实际调整窗口大小,发送WM\_SIZE消息给窗�?
### mCtrlGridObject.resize(行总数,列总数,添加默认标题)

调整表格大小,

默认设置默认列标题为字母、行标题为数�?
### mCtrlGridObject.right

右侧坐标

### mCtrlGridObject.rowCount()

行总数

### mCtrlGridObject.saveScale()

根据控件当前位置、缩放比例，更新控件的设计时位置参数�?
以避免下次窗口缩放自适应调整控件当前位置更改被清除，

控件所有调整位置的属性或成员函数已自动调用此函数�?
### mCtrlGridObject.sendMessage(msg,wParam,lParam)

发送窗口消�?
此函数用法请参�?::User32.SendMessage

### mCtrlGridObject.setCell(行号,列号,MC\_TABLECELL结构�?

设置格列，参数@3为MC\_TABLECELL结构�?
行号省略表示列标题，列号省略表示行标�?
### mCtrlGridObject.setCellAlign(行号,列号,对齐选项)

设置对齐选项,

参数@3应使用一个表指定对齐方式,

对齐表可用left,right,center指定水平对齐选项

可用top bottom,middle指定垂直对齐选项

指定的对齐选项字段值为真时使用该对齐方�?
### mCtrlGridObject.setCellText(行号,列号,文本)

设置列文�?
行号省略表示列标题，列号省略表示行标�?
### mCtrlGridObject.setFocus()

设置焦点

### mCtrlGridObject.setFont(指定字体)

指定LOGFONT字体对象,或逻辑字体句柄

### mCtrlGridObject.setFont(混入字体属�?

```aardio aardio
mCtrlGridObject.setFont(point=10;name="宋体");

```

### mCtrlGridObject.setInterval(间隔时间,回调函数)

创建定时�?
间隔时间以毫秒为单位

### mCtrlGridObject.setParent(控件对象)

改变父窗�?
### mCtrlGridObject.setRect(rc)

设置控件区块位置(::RECT结构�?

### mCtrlGridObject.setRect(rc,true)

设置控件屏幕区块位置(::RECT结构�?

### mCtrlGridObject.setRedraw(false)

禁止重绘

### mCtrlGridObject.setRedraw(true)

恢复重绘

### mCtrlGridObject.setRowHeight(行号,高度)

设置行高�?
### mCtrlGridObject.setSelection()

设置选区

### mCtrlGridObject.setTable(gridTalbe)

修改控件绑定的数据表,

参数应当�?win.ui.ctrl.mCtrl.gridTable对象

### mCtrlGridObject.setTimeout(函数或代�?延时,其他附加参数)

推迟执行指定的函数或代码

此函数异步执行参数中指定的函数，不会阻塞当前代码继续执行�?
延时参数是可选参数，以毫秒为单位，默认为0毫秒

可选用附加参数指定调用延时函数的实�?
返回值为定时器ID

### mCtrlGridObject.show(true)

显示控件

### mCtrlGridObject.tabNext()

setPos(.(x坐标,y坐标,�?�?插入位置,参数) = 调整窗口位置或排�?所有参数可�?
同时指定x,y坐标则移动位�?
同时指定宽高则改变大�?
指定插入位置(句柄或\_HWND前缀常量)则调整Z�?
### mCtrlGridObject.tabNext(移动焦点,是否反向)

获取下一个支持tab控制焦点的控�?
参数@1为true会自动移动焦点到该控�?
参数@2为true则获取上一个控�?否则获取下一个控�?
### mCtrlGridObject.text

控件文本

### mCtrlGridObject.theme

外观主题,例如

winform.button.theme = "Explorer"

winform.button.theme = false

### mCtrlGridObject.threadCallable()

开启此控件的跨线程调用功能

### mCtrlGridObject.top

顶部坐标

### mCtrlGridObject.translateAccelerator

```aardio aardio
mCtrlGridObject.translateAccelerator = function(msg){
    /*返回是否快捷�?/
}

```

### mCtrlGridObject.translateCommand()

这个函数开启消息转发功�?

允许子窗口的\_WM\_COMMAND,\_WM\_CTLCOLORSTATIC等消息给父窗�?

使父窗体可以处理这些消息控制控件的外观、触发命令等

### mCtrlGridObject.tryCreateEmbed("类名",容器对象)

嵌入COM控件,

参数@1也可以指定一个已存在的COM对象,

容器对象为可选参�?

成功返回容器对象,失败返回false,错误信息

### mCtrlGridObject.tryCreateEmbed()

[返回对象:embedObject](../../../../com/_.html#embedObject)

### mCtrlGridObject.update()

重绘invalidate函数指定的区�?
### mCtrlGridObject.wait(等待函数,超时,延时间隔)

循环执行等待函数,并等待返回�?
直到等待函数返回非空�?或存在第二个返回�?或当前窗口关�?
等待函数返回的值就是wait函数的返回�?

如果指定超时,超过指定毫秒时返回null,

除等待函数以�?所有参数可�?
### mCtrlGridObject.width

宽度

### mCtrlGridObject.wndproc

```aardio aardio
mCtrlGridObject.wndproc = function(hwnd,message,wParam,lParam){
    /*窗口消息回调，返回任意非null值阻止默认回�?wndproc重复赋值时追加函数而不是覆盖之前的回调
设为null添除所有消息回调函�?wndproc也可以是一个表,键要为处理的消息,值为对应的消息回调函�?/
}

```

## win.ui.ctrl.mCtrl 成员列表

### win.ui.ctrl.mCtrl.grid

MCtrl 表格控件

### win.ui.ctrl.mCtrl.grid()

MCtrl 表格控件

[返回对象:mCtrlGridObject](#mCtrlGridObject)

### 自动完成常量

\_MC\_GS\_COLUMNHEADERALPHABETIC=0x2000

\_MC\_GS\_COLUMNHEADERMASK=0x3000

\_MC\_GS\_COLUMNHEADERNONE=0x3000

\_MC\_GS\_COLUMNHEADERNORMAL=0

\_MC\_GS\_COLUMNHEADERNUMBERED=0x1000

\_MC\_GS\_COMPLEXSEL=0x300

\_MC\_GS\_DOUBLEBUFFER=4

\_MC\_GS\_EDITLABELS=0x80

\_MC\_GS\_FOCUSEDCELL=0x40

\_MC\_GS\_NOGRIDLINES=2

\_MC\_GS\_NOSEL=0

\_MC\_GS\_NOTABLECREATE=1

\_MC\_GS\_OWNERDATA=8

\_MC\_GS\_RECTSEL=0x200

\_MC\_GS\_RESIZABLECOLUMNS=0x10

\_MC\_GS\_RESIZABLEROWS=0x20

\_MC\_GS\_ROWHEADERALPHABETIC=0x8000

\_MC\_GS\_ROWHEADERMASK=0xC000

\_MC\_GS\_ROWHEADERNONE=0xC000

\_MC\_GS\_ROWHEADERNORMAL=0

\_MC\_GS\_ROWHEADERNUMBERED=0x4000

\_MC\_GS\_SHOWSELALWAYS=0x400

\_MC\_GS\_SINGLESEL=0x100

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/win/ui/ctrl/mCtrl/grid.md)

