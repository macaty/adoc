[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# win.ui.ctrl.listview 库模块帮助文�?
## win.ui.ctrl 成员列表

### win.ui.ctrl.listview()

列表视图

[返回对象:listviewObject](listview.html#listviewObject)

## listviewObject 成员列表

### listviewObject.\_defWindowProc(hwnd,message,wParam,lParam)

用于�?wndproc 回调中提前调用默认消息回调函�?

所有窗口和控件定义�?wndproc 回调以后会自动创建这个函�?

调用此函数以�?wndproc 必须指定�?null 返回�?

以避免再次重复调用默认回调函�?
### listviewObject.\_parentForm

创建该控件的父窗口（win.form对象�?

设计时窗体容器是所有拖放在窗体上的控件�?\_parentForm,

即使窗口移除子窗口样式、更改父子关系，或以 orphanWindow显示,

控件�?\_parentForm 始终都不会改�?
[返回对象:winform](../_.html#winform)

### listviewObject.addCtrl

```aardio aardio
listviewObject.addCtrl(
    edit ={ cls="edit";left=0;top=0;right=50;bottom=50;autoResize=false ;hide=1;edge=1;  }
)

```

### listviewObject.addItem(LVITEM对象,位置)

参数一可以是指定一个或多个LVITEM对象成员的table对象

text成员指定项目文件,也可以是一个指定多列文本的数组

位置参数可省�?默认为count�?
返回新增项行�?
### listviewObject.addItem(文本,位置,图像索引)

位置参数可省�?默认为count�?
图像索引可省�?默认�?1

文本可以是一个指定多列文本的table数组,

如果列文本不是指针、空值则自动转换为字符串,

返回新增项行�?
### listviewObject.adjust

```aardio aardio
listviewObject.adjust = function( cx,cy,wParam ) {
     /*窗口缩放时会自动触发此函数�?cx 参数为窗口宽�?cy 参数为窗口高�?
wParam 参数请参�?_WM_SIZE 消息参数说明,一般不用管�?
所�?win.form 创建的窗体和控件都支持此事件,
重复赋值只会追加而不会覆盖此事件�?一般不建议添加一�?wndproc 仅仅是为了处�? _WM_SIZE 消息�?定义 adjust 事件是更好的选择�?
可主动调用此事件,省略参数�?cx,cy 参数默认设为窗口大小*/
};

```

### listviewObject.bottom

底部坐标

### listviewObject.capture

是否捕获全局鼠标消息

### listviewObject.checkbox

是否在每个项目前显示复选框

注意虚表不存在实际的项也不支持设置项目复选框

### listviewObject.checked

返回已勾选复选框的行索引数组,

此数组内的行索引按实际显示的前后排序,

需要先启用复选框支持

### listviewObject.className

运行时类�?
### listviewObject.clear()

清空所有项

### listviewObject.clear(true)

清空所有项,并且删除所有列

### listviewObject.clearColumnImage()

清除所有列的图像索�?
### listviewObject.clientRect

获取控件客户区块位置(::RECT结构�?

### listviewObject.close()

关闭控件窗口

### listviewObject.cls

设计时类�?
### listviewObject.columnCount

列总数

### listviewObject.count

项目总数

用于实现虚表时可修改此属�?
### listviewObject.delColumn()

删除指定�?
### listviewObject.delItem()

参数为数�?移除指定索引的项�?
### listviewObject.disabled

是否禁用

### listviewObject.each(起始索引,选项)

```aardio aardio
for itemIndex in listviewObject.each(){
    /*遍历所有项*/
}

```

### listviewObject.eachChecked(col)

```aardio aardio
for item,value in listviewObject.eachChecked(){
    /*从后向前倒序遍历所有勾选项,
迭代变量 item 为勾选项行号,
迭代变量 value �? @col 参数所指定列的文本�?@col 参数省略则默认为1*/
}

```

### listviewObject.eachSelected(col)

```aardio aardio
for item,value in listviewObject.eachSelected(){
    /*从后向前倒序遍历所有选中�?
迭代变量 item 为选中项行�?
迭代变量 value �? @col 参数所指定列的文本�?@col 参数省略则默认为1*/
}

```

### listviewObject.editLabel(行序�?

编辑指定�?无参数则编辑选定�?
此函数成功返回编辑文本框句柄

返则返回0

### listviewObject.enableDoubleBuffering()

启用双缓�?

可用于实现虚表时避免拖动时闪�?
### listviewObject.ensureVisible()

滚动视图以确定可以显示参数指定行序号的项,

不指定参数则设置当前选中焦点�?
### listviewObject.fillParent(列序�?

使指定列自适应父窗口宽�?

如果不指定列默认调整最后一�?

用户调整窗口大小时会自动调用此函数调整自适应�?
### listviewObject.findItem(查找文本,起始位置,部分匹配,全局搜索)

使用文本查找匹配�?

除第一个参数外,所有参数可�?

部分匹配仅限于匹配文本开始部�?默认值为true

全局搜索指搜索到最后一项以后转到第一项继续搜�?
### listviewObject.fullRow

是否选中整行

### listviewObject.getChecked()

返回指定索引项是否已勾选复选框，需要启用复选框支持

### listviewObject.getClientRect()

控件客户区块位置(::RECT结构�?

[返回对象:rectObject](../../../global/_.html#rectObject)

### listviewObject.getColumn()

[返回对象:lvcolumnObject](#lvcolumnObject)

### listviewObject.getColumn(列参数表,列序�?

参数一可以为空,或是指定LVCOLUMN结构体成员键值的参数�?

返回LVCOLUMN结构�?
### listviewObject.getColumnImage(col)

获取指定列的图像索引,参数和返回值都是数�?

无图像返回null

### listviewObject.getColumnText()

取指定列文本

### listviewObject.getEditControl()

开始编辑时返回编辑控件,

此控件在完成编辑后会自动销�?不必手动销�?
取消发送\_WM\_CANCELMODE消息即可

[返回对象:editObject](edit.html#editObject)

### listviewObject.getExtended()

获取树视图扩展样�?
### listviewObject.getExtended(\_LVS\_EX)

获取树视图指定扩展样�?
### listviewObject.getFocused(返回字段列号)

返回表示当前焦点项位置的数值。不存在焦点项则返回0�?
如果指定返回字段列号，则�?2 个返回值为指定列的文本值�?
不指定参数时返回值与 selIndex 属性相同�?
设置 selIndex 属性可修改当前焦点�?
### listviewObject.getFont()

控件字体(::LOGFONT结构�?

[返回对象:logfontObject](#logfontObject)

### listviewObject.getHeader()

返回列标题窗口句�?
### listviewObject.getImageList( \_LVSIL )

获取图像列表,

可选使�?_LVSIL_ 前缀常量指定类型

### listviewObject.getItem()

返回LVITEM对象,参数为TVITEM结构体或指定部分成员的table对象.

可选使用参数一指定行号,参考二指定列序�?

不指定项目序�?则取当前焦点节点作为序号

[返回对象:lvitemObject](#lvitemObject)

### listviewObject.getItemRect()

[返回对象:rectObject](../../../global/_.html#rectObject)

### listviewObject.getItemRect(�?�?RECT,选项)

返回表示项目表示项目区块的RECT结构�?

除第一个参数以�?其他参数为可选参�?

如果不指定列则返回所在行区块,

使用\_LVIR\_前缀常量指定选项

### listviewObject.getItemState(项索�?状掩�?)

读取状态�?
### listviewObject.getItemText(�?�?缓冲区长�?

返回指定项指定列文本，列默认值为1,

如果列指定为-1，则返回一个包含所有列文本的数�?

缓冲区最大字符数默认�?20,

不指定行序号则默认取当前选中焦点�?

不指定列则默认设�?

### listviewObject.getNextItem(起始索引,选项)

参数二为一个或多个 _LVNI_ 前缀的常量合�?
默认�?\_LVNI\_ALL

起始索引默认�?

### listviewObject.getNotifyCustomDraw()

[返回对象:NMLVCUSTOMDRAWObject](#NMLVCUSTOMDRAWObject)

### listviewObject.getNotifyCustomDraw(code,ptr)

NM\_CUSTOMDRAW通知消息返回NMLVCUSTOMDRAW结构�?
### listviewObject.getNotifyDispInfo()

[返回对象:LVDISPINFOObject](#LVDISPINFOObject)

### listviewObject.getNotifyDispInfo(code,ptr)

该函数限用于onnotify通知回调函数�?
code参数为通知�?ptr参数为NMHDR指针

如果NMHDR指针指向LV\_DISPINFO对象则返回该对象,否则返回空�?
### listviewObject.getNotifyMessage()

[返回对象:NMLISTVIEWObject](#NMLISTVIEWObject)

### listviewObject.getNotifyMessage(code,ptr)

该函数限用于onnotify通知回调函数�?
code参数为通知�?如果ptr指向NMLISTVIEW对象则返回该对象.

### listviewObject.getParent()

返回父窗�?
[返回对象:staticObject](static.html#staticObject)

### listviewObject.getPos()

返回相对坐标,�?�?
x,y,cx,cy=win.getPos(hwnd)

### listviewObject.getRect()

控件区块位置(::RECT结构�?

### listviewObject.getRect(true)

控件屏幕区块位置(::RECT结构�?

### listviewObject.getSelected(项索�?

指定项是否选中状�?
### listviewObject.getSelection(起始索引,返回字段列号)

获取选中�?返回数�?不存在选中项则返回0

可选指定起始索�?默认�?,

返回字段列号为可选参数，

返回�?为参数为返回行指定列的文本�?
### listviewObject.getTable()

返回数据表�?
如果参数 @1 指定列名数组（被复制为返回表�?fields 字段），

则返回的每行数据都是名值对，否则返回的每行数据都是文本数组�?
如果参数 @1 �?true，则返回的文本数组第一行为列标题文本数组�?
### listviewObject.getTileViewInfo()

返回排列显示相关属�?
[返回对象:tileviewinfoObject](#tileviewinfoObject)

### listviewObject.gridLines

是否显示网格�?
### listviewObject.height

高度

### listviewObject.hitTest(x坐标,y坐标,是否屏幕坐标)

该函数返回指定坐标的行号,参数三可省略,默认为false.

如果不指定任何参�?则自动调�?win.getMessagePos() 获取消息坐标

返回行号,列号,\_LVHT\_前缀的状态常�?
### listviewObject.hwnd

控件句柄

### listviewObject.id

控件ID

### listviewObject.insertColumn(列名,列宽,位置,样式)

第一个参数可以是标题字符�?图像索引,

或者指定LVCOLUMN结构体成员的table对象,

其他参数都是可选参�?

样式使用\_LVCFMT\_前缀的常量指�?

例如\_LVCFMT\_LEFT为文本左对齐,注意第一列只能左对齐,

不指定样式则默认左对�?

如果列宽�?1,则自动调用fillParent(ind)函数填充剩余空间

### listviewObject.items

返回或设置包含所有列表项的数�?
数组的每个项表示一行，每行也必须是包含列文本的数组

返回数组有一个可选字�?checked 包含了所有勾选的�?
### listviewObject.left

左侧坐标

### listviewObject.modifyStyle(remove,add,swpFlags)

修改窗口样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### listviewObject.modifyStyleEx(remove,add,swpFlags)

修改窗口扩展样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS\_EX_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS\_EX_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### listviewObject.onCheckedChanged

```aardio aardio
listviewObject.onCheckedChanged = function(checked,item){
    /*勾选状态变更触发此事件�?checked 为是否勾选，item 为变更项序号*/
}

```

### listviewObject.onClick

```aardio aardio
listviewObject.onClick = function(item,subItem,nmListView){
    /*左键单击项目触发此事件�?item 为变更为焦点的项序号，subItem 为列序号，nmListView �?NMLISTVIEW 结构�?/
}

```

### listviewObject.onDestroy

```aardio aardio
listviewObject.onDestroy = function(){
    /*窗口销毁前触发*/
}

```

### listviewObject.onDoubleClick

```aardio aardio
listviewObject.onDoubleClick = function(item,subItem,nmListView){
    /*左键双击项目触发此事件�?item 为变更为焦点的项序号，subItem 为列序号，nmListView �?NMLISTVIEW 结构�?/
}

```

### listviewObject.onFocusedChanged

```aardio aardio
listviewObject.onFocusedChanged = function(item,subItem,nmListView){
    /*焦点项变更触发此事件�?item 为变更为焦点的项序号，subItem 为列序号，nmListView �?NMLISTVIEW 结构�?/
}

```

### listviewObject.onGetDispItem

```aardio aardio
listviewObject.onGetDispItem = function(item,row,col){
    /*处理 _LVN_GETDISPINFOW 通知消息
参数 @item �?LVITEM 结构�?@row 为当前行�?@col 为当前列�?
返回 item 或包�?item 部分字段则更�?LVITEM 结构�?/
    return {text="要显示的文本"};
}

```

### listviewObject.onItemChanged

```aardio aardio
listviewObject.onItemChanged = function(item,subItem,nmListView){
    /*项目变更触发此事件�?item 为变更为焦点的项序号，subItem 为列序号，nmListView �?NMLISTVIEW 结构�?/
}

```

### listviewObject.onRightClick

```aardio aardio
listviewObject.onRightClick = function(item,subItem,nmListView){
    /*右键点击项目触发此事件�?item 为变更为焦点的项序号，subItem 为列序号，nmListView �?NMLISTVIEW 结构�?/
}

```

### listviewObject.onSelChanged

```aardio aardio
listviewObject.onSelChanged = function(selected,item,subItem,nmListView){
    /*选中项更触发此事件�?selected 为是否选中，item 为变更项序号�?subItem 为列序号，nmListView �?NMLISTVIEW 结构�?/
}

```

### listviewObject.oncommand

```aardio aardio
listviewObject.oncommand = function(id,event){
    /*命令事件触发*/
}

```

### listviewObject.onnotify

```aardio aardio
listviewObject.onnotify = function(id,code,ptr){
    /*通知事件触发*/
}

```

### listviewObject.orphanWindow(transparent,hwndBuddy,borderless)

创建悬浮窗口�?
悬浮窗口是模仿子窗口外观效果的独立窗口，父窗口可自动调整子窗口到设定位置�?
可选参�?@transparent �?true 则转换为分层透明窗口�?
可选利�?@hwndBuddy 参数指定外部进程窗口句柄的并附加在内部控件上以实现相同的效果�?
伙伴窗口总是会保持在悬浮窗口前面，并保持相同的大小、位置�?
可重复调用此函数更换伙伴窗口，旧的伙伴窗口必须自行关闭�?
可选指�?@borderless 参数 �?true 以移�?@hwndBuddy 的窗口边框�?
### listviewObject.postMessage(msg,wParam,lParam)

投递窗口消息到消息队列�?
此函数用法请参�?::User32.PostMessage

### listviewObject.redraw()

刷新

### listviewObject.replaceItems()

替换所有列表项�?
参数@1 指定包含所有列表项的数组，格式�?items 属性相同�?
数组的每个项表示一行，每行也必须是包含列文本的数组�?
数组可以有一个可选字�?checked 包含了所有勾选的行�?
此函数不会事先清空列表，�?items 则会事先清空列表�?
当每次替换需要删除的项数较少时，此函数可避免清空导致的闪烁�?
建议先用 enableDoubleBuffering 函数启用双缓�?
### listviewObject.right

右侧坐标

### listviewObject.selIndex

当前获得控件内部输入焦点的选中项�?
这指的是最后一次用鼠标点选的项�?
如果要设置控件本身为输入焦点请调�?setFocus 函数

### listviewObject.selected

所有选中项目索引的数�?

注意是选中列表项而不是指勾选复选框

设为 null 或空表清除所有选中�?
### listviewObject.sendMessage(msg,wParam,lParam)

发送窗口消�?
此函数用法请参�?::User32.SendMessage

### listviewObject.setChecked(索引,是否勾�?

勾选指定索引项前面的复选框，需要启用复选框支持

参数@1�?则设置全部项�?

参数@2省略则默认为true

### listviewObject.setColumn({cx=100},列序�?

改变列宽

### listviewObject.setColumn(列参数表,列序�?

参数一指定LVCOLUMN结构体成员键值的参数�?

也可以是LVCOLUMN结构体对�?自动设置掩码参数.

### listviewObject.setColumnImage(col,iImage,fmt)

使用col指定列索引设置该列的图像索引为iImage,

第一列col的索引值为1,但图像列表的第一个图像索引为0,

可选用fmt指定图像显示位置,此参数用法参考此函数源码

### listviewObject.setColumnImageList(imgList)

设置图像列表,

参数可以是图像列表句�?也可以传入win.imageList对象

### listviewObject.setColumnText(位置,文本)

设置指定列文�?
### listviewObject.setColumnWidth(列宽,列序�?...)

设置列宽，可指定一个或多个列序号�?
这里不能指定宽度�?-1 �?
### listviewObject.setColumns(column1,column2,...)

参数用不定个数的字符串指定要显示的列

如果参数@1为空则清空所有列

### listviewObject.setColumns(columns,widths,alignments)

参数@1用一个字符串数组指定要显示的�?
如果参数@1为空则清空所有列,

可选在 @widths 参数用一个数组指定各列宽�?

可选在 @alignments 参数用一个数组指定各列对齐选项,

各列可用参数�?insertColumn 函数相同

### listviewObject.setExtended(\_LVS\_EX)

启用树视图指定扩展样�?
### listviewObject.setExtended(\_LVS\_EX,false)

取消树视图指定扩展样�?
### listviewObject.setFocus()

设置窗口的焦点到当前控件�?
如果要改变控件内部的焦点到某一行，请设�?selIndex 属�?
### listviewObject.setFont(指定字体)

指定LOGFONT字体对象,或逻辑字体句柄

### listviewObject.setFont(混入字体属�?

```aardio aardio
listviewObject.setFont(point=10;name="宋体");

```

### listviewObject.setImageList( imageList,\_LVSIL )

指定图像列表,

可选使�?_LVSIL_ 前缀常量指定类型

listview控件在销毁时将自动销毁最后一次指定的图像列表�?
通过替换并且不再使用的图像列表由用户负责销�?
### listviewObject.setItem(LVITEM对象,行序�?列序�?

更新项节�?参数为LVITEM结构体或指定部分成员的table对象

如果参数未指定节点序�?则取当前焦点节点序号

成功返回true;

此函数可自动检测非空成员并自动设定相应mask�?
### listviewObject.setItemPos(项索�?x,y)

设置图标项坐�?
### listviewObject.setItemState(项索�?状态位,掩码)

设置状�?参数三如果省略则使用参数二的�?

参数@1�?则设置全部项�?

### listviewObject.setItemText(文本,�?�?

设置项目指定列文�?

参数一也可是指定多列文本的数组

设置的文本如果不是指针或空值则自动转换为字符串,

不指定行序号则默认取当前选中焦点�?

不指定列则默认设�?

### listviewObject.setNotifyDispInfo(ptr,dispinfo)

参数@1为更新目标指�?

参数@2必须是getNotifyDispInfo函数的返回�?
### listviewObject.setParent(控件对象)

改变父窗�?
### listviewObject.setPos(x坐标,y坐标,�?�?插入位置,参数)

调整窗口位置或排�?所有参数可�?
同时指定x,y坐标则移动位�?
同时指定宽高则改变大�?
指定插入位置(句柄或\_HWND前缀常量)则调整Z�?
### listviewObject.setRect(rc)

设置控件区块位置(::RECT结构�?

### listviewObject.setRect(rc,true)

设置控件屏幕区块位置(::RECT结构�?

### listviewObject.setRedraw(false)

禁止重绘

### listviewObject.setRedraw(true)

恢复重绘

### listviewObject.setSelected(项索�?

选中�?注意是选中列表项而不是勾选复选框

### listviewObject.setSelected(项索�?false)

取消选中�?注意是选中而不是勾选复选框

### listviewObject.setTable

�?listview 控件显示数据表（包含名值对的对象或数组组成的数组）�?
此函数会自动清空控件之前的所有项�?
如果没有创建任何列，则自动创建标题列�?
如果要重新创建列，请先调�?clear 函数并指定参数为 true 以清空原来的列�?
### listviewObject.setTable(dataTable)

参数 @dataTable 指定要加载的数据表�?
数据表应当包含行组成的数组�?
数据行可以是数组，也可以是名值，值用 tostring 转为文本显示�?
可选通过数据表的 fields 字段指定要显示的索引数组（键名或索引数值）�?
如果视图控件的标题列为空，则用显示键名（或数组值）创建标题列�?
如果数据行为数组，第一行填充到标题列以后，默认从第二行加载数据�?
可用 startIndex 属性或元属性自定义要加载的起始行�?
可用 length 属性自定义要加载的行数，默认加载所有行�?
sqlite,access,sqlServer 等数据库对象�?
提供�?getTable 函数可获取通过 fields 字段指定列名数组的数据表�?
### listviewObject.setTileViewInfo()

设置排列显示相关属�?
### listviewObject.show(true)

显示控件

### listviewObject.theme

外观主题,例如

winform.button.theme = "Explorer"

winform.button.theme = false

### listviewObject.threadCallable()

开启此控件的跨线程调用功能

### listviewObject.top

顶部坐标

### listviewObject.translateCommand()

允许转发转发子窗口的命令（\_WM\_COMMAND）与通知（\_WM\_NOTIFY）消息，

避免子窗�?oncommand，onnotify 等回调失效�?
同时会处理子窗口�?\_WM\_CTLCOLORSTATIC 等消息，

以避免部分外观属性失�?
### listviewObject.valid

窗口是否有效�?
窗口未关闭返�?true �?
窗口已关闭或正在关闭返回 false

### listviewObject.width

宽度

### listviewObject.wndproc

```aardio aardio
listviewObject.wndproc = function(hwnd,message,wParam,lParam){
    /*窗口消息回调，返回任意非null值阻止默认回�?wndproc重复赋值时追加函数而不是覆盖之前的回调
设为null添除所有消息回调函�?wndproc也可以是一个表,键要为处理的消息,值为对应的消息回调函�?/
}

```

## LVDISPINFOObject 成员列表

### LVDISPINFOObject.hdr

[返回对象:nmhdrObject](#nmhdrObject)

### LVDISPINFOObject.item

[返回对象:lvitemObject](#lvitemObject)

## NMLISTVIEWObject 成员列表

### NMLISTVIEWObject.hdr

[返回对象:nmhdrObject](#nmhdrObject)

### NMLISTVIEWObject.iItem

鼠标指向项的行号

没有使用则为0

### NMLISTVIEWObject.iSubItem

鼠标指向项的列序�?
没有使用则为0

### NMLISTVIEWObject.lParam

附加参数

### NMLISTVIEWObject.ptAction

[返回对象:pointObject](#pointObject)

### NMLISTVIEWObject.uChanged

类似LVITEM结构体中的mask成员

以LVIF\_前缀的常量标明改变的属�?
### NMLISTVIEWObject.uNewState

改变后状�?
由\_LVIS\_作为前缀的常量指�?
### NMLISTVIEWObject.uOldState

改变前状�?
由\_LVIS\_作为前缀的常量指�?
## NMLVCUSTOMDRAWObject 成员列表

### NMLVCUSTOMDRAWObject.clrFace

```aardio aardio
clrFace

```

### NMLVCUSTOMDRAWObject.clrText

文字颜色

### NMLVCUSTOMDRAWObject.clrTextBk

文字背景�?
### NMLVCUSTOMDRAWObject.dwItemType

```aardio aardio
dwItemType

```

### NMLVCUSTOMDRAWObject.iIconEffect

```aardio aardio
iIconEffect

```

### NMLVCUSTOMDRAWObject.iIconPhase

```aardio aardio
iIconPhase

```

### NMLVCUSTOMDRAWObject.iPartId

```aardio aardio
iPartId

```

### NMLVCUSTOMDRAWObject.iStateId

```aardio aardio
iStateId

```

### NMLVCUSTOMDRAWObject.iSubItem

列序�?
### NMLVCUSTOMDRAWObject.nmcd.dwDrawStage

绘图状�?
### NMLVCUSTOMDRAWObject.nmcd.dwItemSpec

行序�?
### NMLVCUSTOMDRAWObject.nmcd.hdc

设置句柄

### NMLVCUSTOMDRAWObject.nmcd.hdr

[返回对象:nmhdrObject](#nmhdrObject)

### NMLVCUSTOMDRAWObject.nmcd.lItemlParam

自定义数据，LPARAM 参数

### NMLVCUSTOMDRAWObject.nmcd.rc

[返回对象:rectObject](../../../global/_.html#rectObject)

### NMLVCUSTOMDRAWObject.nmcd.uItemState

状态值，例如 \_CDIS\_FOCUS

### NMLVCUSTOMDRAWObject.rcText

[返回对象:rectObject](../../../global/_.html#rectObject)

### NMLVCUSTOMDRAWObject.uAlign

对齐

### NMLVCUSTOMDRAWObject.update()

更新数据

## lvcolumnObject 成员列表

### lvcolumnObject.cchTextMax

文本缓冲区长�?
### lvcolumnObject.cx

宽度

### lvcolumnObject.fmt

样式

### lvcolumnObject.iImage

图像索引

### lvcolumnObject.iOrder

序号

### lvcolumnObject.iSubItem

列号

### lvcolumnObject.mask

掩码;

### lvcolumnObject.text

文本指针

注意该值是指针类型而不是字符串类型

转换为字符串必须首先判断mask包含4/\*\_LVCF\_TEXT\*/

## lvitemObject 成员列表

### lvitemObject.cColumns

列数�?
### lvitemObject.cchTextMax

文本长度

### lvitemObject.iGroupId

组ID

### lvitemObject.iImage

图像索引

### lvitemObject.iIndent

缩进

### lvitemObject.iItem

�?
### lvitemObject.iSubItem

�?
### lvitemObject.lParam

附加�?
### lvitemObject.mask

掩码

### lvitemObject.puColumns

[返回对象:pointObject](#pointObject)

### lvitemObject.state

状态码

### lvitemObject.stateMask

状态掩�?
### lvitemObject.text

文本指针

注意该值是指针类型而不是字符串类型

转换为字符串必须首先判断mask是否包含1/\*\_LVIF\_TEXT\*/

## tileviewinfoObject 成员列表

### tileviewinfoObject.cLines

行数

### tileviewinfoObject.dwFlags

```aardio aardio
tileviewinfoObject.dwFlags = _LVTVIF ;

```

### tileviewinfoObject.dwMask

```aardio aardio
tileviewinfoObject.dwMask = _LVTVIM ;

```

### tileviewinfoObject.rcLabelMargin

[返回对象:rectObject](../../../global/_.html#rectObject)

### tileviewinfoObject.sizeTile

[返回对象:sizeObject](#sizeObject)

### 自动完成常量

\_CDIS\_CHECKED=8

\_CDIS\_DEFAULT=0x20

\_CDIS\_DISABLED=4

\_CDIS\_FOCUS=0x10

\_CDIS\_GRAYED=2

\_CDIS\_HOT=0x40

\_CDIS\_INDETERMINATE=0x100

\_CDIS\_MARKED=0x80

\_CDIS\_SELECTED=1

\_CDIS\_SHOWKEYBOARDCUES=0x200

\_LVCFMT\_BITMAP\_ON\_RIGHT=0x1000

\_LVCFMT\_CENTER=2

\_LVCFMT\_COL\_HAS\_IMAGES=0x8000

\_LVCFMT\_FILL=0x200000

\_LVCFMT\_FIXED\_RATIO=0x80000

\_LVCFMT\_FIXED\_WIDTH=0x100

\_LVCFMT\_IMAGE=0x800

\_LVCFMT\_JUSTIFYMASK=3

\_LVCFMT\_LEFT=0x0

\_LVCFMT\_LINE\_BREAK=0x100000

\_LVCFMT\_NO\_DPI\_SCALE=0x40000

\_LVCFMT\_NO\_TITLE=0x800000

\_LVCFMT\_RIGHT=1

\_LVCFMT\_SPLITBUTTON=0x1000000

\_LVCFMT\_TILE\_PLACEMENTMASK=0x300000

\_LVCFMT\_WRAP=0x400000

\_LVCF\_DEFAULTWIDTH=0x80

\_LVCF\_FMT=1

\_LVCF\_IDEALWIDTH=0x100

\_LVCF\_IMAGE=0x10

\_LVCF\_MINWIDTH=0x40

\_LVCF\_ORDER=0x20

\_LVCF\_SUBITEM=8

\_LVCF\_TEXT=4

\_LVCF\_WIDTH=2

\_LVFI\_NEARESTXY=0x40

\_LVFI\_PARAM=1

\_LVFI\_STRING=2

\_LVFI\_SUBSTRING=4

\_LVFI\_WRAP=0x20

\_LVHT\_ABOVE=8

\_LVHT\_BELOW=0x10

\_LVHT\_NOWHERE=1

\_LVHT\_ONITEM=0xE

\_LVHT\_ONITEMICON=2

\_LVHT\_ONITEMLABEL=4

\_LVHT\_ONITEMSTATEICON=8

\_LVHT\_TOLEFT=0x40

\_LVHT\_TORIGHT=0x20

\_LVIF\_COLFMT=0x10000

\_LVIF\_COLUMNS=0x200

\_LVIF\_GROUPID=0x100

\_LVIF\_IMAGE=2

\_LVIF\_INDENT=0x10

\_LVIF\_NORECOMPUTE=0x800

\_LVIF\_PARAM=4

\_LVIF\_STATE=8

\_LVIF\_TEXT=1

\_LVIR\_BOUNDS=0

\_LVIR\_ICON=1

\_LVIR\_LABEL=2

\_LVIR\_SELECTBOUNDS=3

\_LVIS\_ACTIVATING=0x20

\_LVIS\_CUT=4

\_LVIS\_DROPHILITED=8

\_LVIS\_FOCUSED=1

\_LVIS\_GLOW=0x10

\_LVIS\_OVERLAYMASK=0xF00

\_LVIS\_SELECTED=2

\_LVIS\_STATEIMAGEMASK=0xF000

\_LVM\_APPROXIMATEVIEWRECT=0x1040

\_LVM\_ARRANGE=0x1016

\_LVM\_CANCELEDITLABEL=0x10B3

\_LVM\_CREATEDRAGIMAGE=0x1021

\_LVM\_DELETEALLITEMS=0x1009

\_LVM\_DELETECOLUMN=0x101C

\_LVM\_DELETEITEM=0x1008

\_LVM\_EDITLABEL=0x1017

\_LVM\_ENABLEGROUPVIEW=0x109D

\_LVM\_ENSUREVISIBLE=0x1013

\_LVM\_FINDITEM=0x100D

\_LVM\_FIRST=0x1000

\_LVM\_GETBKCOLOR=0x1000

\_LVM\_GETBKIMAGE=0x1045

\_LVM\_GETCALLBACKMASK=0x100A

\_LVM\_GETCOLUMN=0x1019

\_LVM\_GETCOLUMNORDERARRAY=0x103B

\_LVM\_GETCOLUMNW=0x105F

\_LVM\_GETCOLUMNWIDTH=0x101D

\_LVM\_GETCOUNTPERPAGE=0x1028

\_LVM\_GETEDITCONTROL=0x1018

\_LVM\_GETEMPTYTEXT=0x10CC

\_LVM\_GETEXTENDEDLISTVIEWSTYLE=0x1037

\_LVM\_GETFOCUSEDGROUP=0x105D

\_LVM\_GETFOOTERINFO=0x10CE

\_LVM\_GETFOOTERITEM=0x10D0

\_LVM\_GETFOOTERITEMRECT=0x10CF

\_LVM\_GETFOOTERRECT=0x10CD

\_LVM\_GETGROUPCOUNT=0x1098

\_LVM\_GETGROUPINFO=0x1095

\_LVM\_GETGROUPINFOBYINDEX=0x1099

\_LVM\_GETGROUPMETRICS=0x109C

\_LVM\_GETGROUPRECT=0x1062

\_LVM\_GETGROUPSTATE=0x105C

\_LVM\_GETHEADER=0x101F

\_LVM\_GETHOTCURSOR=0x103F

\_LVM\_GETHOTITEM=0x103D

\_LVM\_GETHOVERTIME=0x1048

\_LVM\_GETIMAGELIST=0x1002

\_LVM\_GETINSERTMARK=0x10A7

\_LVM\_GETINSERTMARKCOLOR=0x10AB

\_LVM\_GETINSERTMARKRECT=0x10A9

\_LVM\_GETISEARCHSTRING=0x1034

\_LVM\_GETITEMCOUNT=0x1004

\_LVM\_GETITEMINDEXRECT=0x10D1

\_LVM\_GETITEMPOSITION=0x1010

\_LVM\_GETITEMRECT=0x100E

\_LVM\_GETITEMSPACING=0x1033

\_LVM\_GETITEMSTATE=0x102C

\_LVM\_GETITEMTEXT=0x1073

\_LVM\_GETITEMW=0x104B

\_LVM\_GETNEXTITEM=0x100C

\_LVM\_GETNEXTITEMINDEX=0x10D3

\_LVM\_GETNUMBEROFWORKAREAS=0x1049

\_LVM\_GETORIGIN=0x1029

\_LVM\_GETOUTLINECOLOR=0x10B0

\_LVM\_GETSELECTEDCOLUMN=0x10AE

\_LVM\_GETSELECTEDCOUNT=0x1032

\_LVM\_GETSELECTIONMARK=0x1042

\_LVM\_GETSTRINGWIDTH=0x1011

\_LVM\_GETSUBITEMRECT=0x1038

\_LVM\_GETTEXTBKCOLOR=0x1025

\_LVM\_GETTEXTCOLOR=0x1023

\_LVM\_GETTILEINFO=0x10A5

\_LVM\_GETTILEVIEWINFO=0x10A3

\_LVM\_GETTOOLTIPS=0x104E

\_LVM\_GETTOPINDEX=0x1027

\_LVM\_GETUNICODEFORMAT=0x2006

\_LVM\_GETVIEW=0x108F

\_LVM\_GETVIEWRECT=0x1022

\_LVM\_GETWORKAREAS=0x1046

\_LVM\_HASGROUP=0x10A1

\_LVM\_HITTEST=0x1012

\_LVM\_INSERTCOLUMN=0x1061

\_LVM\_INSERTGROUP=0x1091

\_LVM\_INSERTGROUPSORTED=0x109F

\_LVM\_INSERTITEM=0x104D

\_LVM\_INSERTMARKHITTEST=0x10A8

\_LVM\_ISGROUPVIEWENABLED=0x10AF

\_LVM\_ISITEMVISIBLE=0x10B6

\_LVM\_MAPIDTOINDEX=0x10B5

\_LVM\_MAPINDEXTOID=0x10B4

\_LVM\_MOVEGROUP=0x1097

\_LVM\_MOVEITEMTOGROUP=0x109A

\_LVM\_REDRAWITEMS=0x1015

\_LVM\_REMOVEALLGROUPS=0x10A0

\_LVM\_REMOVEGROUP=0x1096

\_LVM\_SCROLL=0x1014

\_LVM\_SETBKCOLOR=0x1001

\_LVM\_SETBKIMAGE=0x1044

\_LVM\_SETCALLBACKMASK=0x100B

\_LVM\_SETCOLUMN=0x101A

\_LVM\_SETCOLUMNORDERARRAY=0x103A

\_LVM\_SETCOLUMNWIDTH=0x101E

\_LVM\_SETGROUPINFO=0x1093

\_LVM\_SETGROUPMETRICS=0x109B

\_LVM\_SETHOTCURSOR=0x103E

\_LVM\_SETHOTITEM=0x103C

\_LVM\_SETHOVERTIME=0x1047

\_LVM\_SETICONSPACING=0x1035

\_LVM\_SETIMAGELIST=0x1003

\_LVM\_SETINFOTIP=0x10AD

\_LVM\_SETINSERTMARK=0x10A6

\_LVM\_SETINSERTMARKCOLOR=0x10AA

\_LVM\_SETITEMCOUNT=0x102F

\_LVM\_SETITEMINDEXSTATE=0x10D2

\_LVM\_SETITEMPOSITION=0x100F

\_LVM\_SETITEMPOSITION32=0x1031

\_LVM\_SETITEMSTATE=0x102B

\_LVM\_SETITEMTEXT=0x1074

\_LVM\_SETITEMW=0x104C

\_LVM\_SETOUTLINECOLOR=0x10B1

\_LVM\_SETSELECTEDCOLUMN=0x108C

\_LVM\_SETSELECTIONMARK=0x1043

\_LVM\_SETTEXTBKCOLOR=0x1026

\_LVM\_SETTEXTCOLOR=0x1024

\_LVM\_SETTILEINFO=0x10A4

\_LVM\_SETTILEVIEWINFO=0x10A2

\_LVM\_SETTOOLTIPS=0x104A

\_LVM\_SETUNICODEFORMAT=0x2005

\_LVM\_SETVIEW=0x108E

\_LVM\_SETWORKAREAS=0x1041

\_LVM\_SORTGROUPS=0x109E

\_LVM\_SORTITEMS=0x1030

\_LVM\_SORTITEMSEX=0x1051

\_LVM\_SUBITEMHITTEST=0x1039

\_LVM\_UPDATE=0x102A

\_LVNI\_ABOVE=0x100

\_LVNI\_ALL=0x0

\_LVNI\_BELOW=0x200

\_LVNI\_CUT=4

\_LVNI\_DIRECTIONMASK=0xF00

\_LVNI\_DROPHILITED=8

\_LVNI\_FOCUSED=1

\_LVNI\_PREVIOUS=0x20

\_LVNI\_SAMEGROUPONLY=0x80

\_LVNI\_SELECTED=2

\_LVNI\_STATEMASK=0xF

\_LVNI\_TOLEFT=0x400

\_LVNI\_TORIGHT=0x800

\_LVNI\_VISIBLEONLY=0x40

\_LVNI\_VISIBLEORDER=0x10

\_LVN\_BEGINDRAG=0xFFFFFF93

\_LVN\_BEGINLABELEDIT=0xFFFFFF97

\_LVN\_BEGINLABELEDITW=0xFFFFFF51

\_LVN\_BEGINRDRAG=0xFFFFFF91

\_LVN\_COLUMNCLICK=0xFFFFFF94

\_LVN\_COLUMNDROPDOWN=0xFFFFFF5C

\_LVN\_COLUMNOVERFLOWCLICK=0xFFFFFF5A

\_LVN\_DELETEALLITEMS=0xFFFFFF98

\_LVN\_DELETEITEM=0xFFFFFF99

\_LVN\_ENDLABELEDIT=0xFFFFFF96

\_LVN\_ENDLABELEDITW=0xFFFFFF50

\_LVN\_FIRST=0xFFFFFF9C

\_LVN\_GETDISPINFOW=0xFFFFFF4F

\_LVN\_HOTTRACK=0xFFFFFF87

\_LVN\_INSERTITEM=0xFFFFFF9A

\_LVN\_ITEMACTIVATE=0xFFFFFF8E

\_LVN\_ITEMCHANGED=0xFFFFFF9B

\_LVN\_ITEMCHANGING=0xFFFFFF9C

\_LVN\_KEYDOWN=0xFFFFFF65

\_LVN\_LAST=FFFFFF39

\_LVN\_MARQUEEBEGIN=0xFFFFFF64

\_LVN\_ODCACHEHINT=0xFFFFFF8F

\_LVN\_ODFINDITEM=0xFFFFFF68

\_LVN\_ODSTATECHANGED=0xFFFFFF8D

\_LVN\_SETDISPINFO=0xFFFFFF69

\_LVN\_SETDISPINFOW=0xFFFFFF4E

\_LVSIL\_GROUPHEADER=3

\_LVSIL\_NORMAL=0

\_LVSIL\_SMALL=1

\_LVSIL\_STATE=2

\_LVS\_ALIGNLEFT=0x800

\_LVS\_ALIGNMASK=0xC00

\_LVS\_ALIGNTOP=0x0

\_LVS\_AUTOARRANGE=0x100

\_LVS\_EDITLABELS=0x200

\_LVS\_EX\_AUTOAUTOARRANGE=0x1000000

\_LVS\_EX\_AUTOCHECKSELECT=0x8000000

\_LVS\_EX\_AUTOSIZECOLUMNS=0x10000000

\_LVS\_EX\_BORDERSELECT=0x8000

\_LVS\_EX\_CHECKBOXES=4

\_LVS\_EX\_COLUMNOVERFLOW=0x80000000

\_LVS\_EX\_COLUMNSNAPPOINTS=0x40000000

\_LVS\_EX\_DOUBLEBUFFER=0x10000

\_LVS\_EX\_FLATSB=0x100

\_LVS\_EX\_FULLROWSELECT=0x20

\_LVS\_EX\_GRIDLINES=1

\_LVS\_EX\_HEADERDRAGDROP=0x10

\_LVS\_EX\_HEADERINALLVIEWS=0x2000000

\_LVS\_EX\_HIDELABELS=0x20000

\_LVS\_EX\_INFOTIP=0x400

\_LVS\_EX\_JUSTIFYCOLUMNS=0x200000

\_LVS\_EX\_LABELTIP=0x4000

\_LVS\_EX\_MULTIWORKAREAS=0x2000

\_LVS\_EX\_ONECLICKACTIVATE=0x40

\_LVS\_EX\_REGIONAL=0x200

\_LVS\_EX\_SIMPLESELECT=0x100000

\_LVS\_EX\_SINGLEROW=0x40000

\_LVS\_EX\_SNAPTOGRID=0x80000

\_LVS\_EX\_SUBITEMIMAGES=2

\_LVS\_EX\_TRACKSELECT=8

\_LVS\_EX\_TRANSPARENTBKGND=0x400000

\_LVS\_EX\_TRANSPARENTSHADOWTEXT=0x800000

\_LVS\_EX\_TWOCLICKACTIVATE=0x80

\_LVS\_EX\_UNDERLINECOLD=0x1000

\_LVS\_EX\_UNDERLINEHOT=0x800

\_LVS\_ICON=0x0

\_LVS\_LIST=3

\_LVS\_NOCOLUMNHEADER=0x4000

\_LVS\_NOLABELWRAP=0x80

\_LVS\_NOSCROLL=0x2000

\_LVS\_NOSORTHEADER=0x8000

\_LVS\_OWNERDATA=0x1000

\_LVS\_OWNERDRAWFIXED=0x400

\_LVS\_REPORT=1

\_LVS\_SHAREIMAGELISTS=0x40

\_LVS\_SHOWSELALWAYS=8

\_LVS\_SINGLESEL=4

\_LVS\_SMALLICON=2

\_LVS\_SORTASCENDING=0x10

\_LVS\_SORTDESCENDING=0x20

\_LVS\_TYPEMASK=3

\_LVS\_TYPESTYLEMASK=0xFC00

\_LVTVIF\_AUTOSIZE=0x0

\_LVTVIF\_EXTENDED=4

\_LVTVIF\_FIXEDHEIGHT=2

\_LVTVIF\_FIXEDSIZE=3

\_LVTVIF\_FIXEDWIDTH=1

\_LVTVIM\_COLUMNS=2

\_LVTVIM\_LABELMARGIN=4

\_LVTVIM\_TILESIZE=1

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/win/ui/ctrl/listview.md)

