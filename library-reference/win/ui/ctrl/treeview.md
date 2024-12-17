[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# win.ui.ctrl.treeview 库模块帮助文�?
## win.ui.ctrl 成员列表

### win.ui.ctrl.treeview()

树形视图控件

[返回对象:treeviewObject](#treeviewObject)

## treeviewObject 成员列表

### treeviewObject.\_parentForm

控件所在的父窗�?指win.form对象)

[返回对象:winform](../_.html#winform)

### treeviewObject.addCtrl

```aardio aardio
treeviewObject.addCtrl(
    button={ cls="button";text="button";left=33;top=32;right=126;bottom=81;autoResize=false }
)

```

### treeviewObject.adjust

```aardio aardio
treeviewObject.adjust = function( cx,cy,wParam ) {
    /*窗口缩放时会自动触发此函数�?cx 参数为窗口宽�?cy 参数为窗口高�?
wParam 参数请参�?_WM_SIZE 消息参数说明,一般不用管�?
所�?win.form 创建的窗体和控件都支持此事件,
重复赋值只会追加而不会覆盖此事件�?一般不建议添加一�?wndproc 仅仅是为了处�? _WM_SIZE 消息�?定义 adjust 事件是更好的选择�?
可主动调用此事件,省略参数�?cx,cy 参数默认设为窗口大小*/
};

```

### treeviewObject.bottom

底部坐标

### treeviewObject.capture

是否捕获全局鼠标消息

### treeviewObject.checkAll(节点句柄,是否选中)

勾选或取消勾选所有下级子节点

并且更新所有上级父节点的勾选状态为：是否有任意的子节点是勾选状�?
参数@1如果不指定则表示根节�?\_TVI\_ROOT)

参数@2不指定则默认赋值为true

### treeviewObject.className

运行时类�?
### treeviewObject.clear

清空节点

### treeviewObject.clear()

清空所有节�?
### treeviewObject.clear(hItem)

清空参数指定节点的所有子节点,

@hItem 参数指定节点句柄

### treeviewObject.close()

关闭控件窗口

### treeviewObject.cls

设计时类�?
### treeviewObject.collapse(hItem)

折叠�?
参数为节点句�?省略则取当前选中�?
### treeviewObject.collapseReset(hItem)

折叠并删除子�?
参数为节点句�?省略则取当前选中�?
### treeviewObject.count

获取项目总数

### treeviewObject.delItem(hItem节点句柄)

删除节点

参数:节点句柄

### treeviewObject.disabled

是否禁用

### treeviewObject.each(父节点句�?

```aardio aardio
for hChild in treeviewObject.each(){
    /*遍历父节点句柄的下级子级�?不包含子节点的子节点*/
}

```

### treeviewObject.editLabel(hItem)

开始编辑项,参数为节点句�?
### treeviewObject.endEdit()

结束编辑�?
### treeviewObject.endEdit(true)

结束编辑并取�?
### treeviewObject.ensureVisible(hItem)

确保指定项目是可见的,通过展开父项目或滚动树型控件�?

参数为节点句�?
### treeviewObject.enum(回调函数,节点句柄)

```aardio aardio
treeviewObject.enum(
    function(hItem,parent){
        /*枚举所有下级子节点,
hItem为当前节�?parent为当前节点的父节�?返回false停止枚举*/
    }
)

```

### treeviewObject.enumParent(回调函数,节点句柄)

```aardio aardio
treeviewObject.enumParent(
    function(parent,child){
        /*枚举所有上级父节点,
parent为当前父节点,child为该节点的子节点
child是上一次枚举到的父节点或者自�?返回false停止枚举*/
    }
)

```

### treeviewObject.expand(hItem)

展开�?
参数为节点句�?省略则取当前选中�?
### treeviewObject.expandAll(hItem)

展开指定�?并展开指定项的所有下级子级点

包含子级点的所有下级子节点都会被展开

### treeviewObject.expandPartial(hItem)

部分展开

参数为节点句�?省略则取当前选中�?
### treeviewObject.expandTo(hItem)

展开项以及其所有上级父节点

参数为节点句�?省略则取当前选中�?
### treeviewObject.find(父节�?"子项标题",...)

查找子项,展开上级父节�?

可以用多个文本参数多级向下查找子�?

父节点参数可省略,参数也可以是一个字符串数组

### treeviewObject.findPath(父节�?"路径\\子项")

按路径查找子�?展开上级父节�?
父节点参数可省略不写,默认为根节点,

### treeviewObject.getChecked(hItem节点句柄)

返回指定项的复选框是否勾�?
### treeviewObject.getChildItem(hItem节点句柄)

返回子节�?
参数:节点句柄

### treeviewObject.getChildren(hItem)

返回包含节点所有子节点句柄的数�?

@hItem 参数指定节点句柄

### treeviewObject.getClientRect()

控件客户区块位置(::RECT结构�?

[返回对象:rectObject](../../../global/_.html#rectObject)

### treeviewObject.getEditControl()

开始编辑时返回编辑控件,

此控件在完成编辑后会自动销�?不必手动销�?
取消发送\_WM\_CANCELMODE消息即可

[返回对象:editObject](edit.html#editObject)

### treeviewObject.getEditHwnd()

返回编辑文本框句�?

### treeviewObject.getFirst()

返回树视图中的第一个节�?
也即\_TVI\_ROOT的第一个子节点

### treeviewObject.getFirstVisible()

返回第一个可见节�?
参数:节点句柄

### treeviewObject.getFont()

控件字体(::LOGFONT结构�?

[返回对象:logfontObject](#logfontObject)

### treeviewObject.getImageList( \_TVSIL )

获取图像列表,

可选使�?_LVSIL_ 前缀常量指定类型

### treeviewObject.getItem()

返回TVITEM对象,参数为TVITEM结构体或指定部分成员的table对象.

参数一也可以是空�?或树节点句柄

如果参数未指定节点句�?则取当前选中节点

[返回对象:tvitemObject](#tvitemObject)

### treeviewObject.getItemData(hItem)

返回节点关联数据

### treeviewObject.getItemPath(节点句柄)

返回节点路径,以反斜杠分隔父子项目文本

省略节点参数则取当前选中节点

### treeviewObject.getItemRect(hItem)

返回句柄指定节点整行区块(RECT对象)

省略节点句柄则取当前选中节点

### treeviewObject.getItemRect(hItem,true)

返回句柄指定节点文本区块(RECT对象)

省略节点句柄则取当前选中节点

### treeviewObject.getItemText(节点句柄,缓冲区长�?

返回节点文本

省略节点参数则取当前选中节点

缓冲区长度参数可省略,默认�?00

### treeviewObject.getNextItem(hItem节点句柄)

返回下一个节�?

第二个参数可选使�?_TVNI_ 前缀的常量指定选项

### treeviewObject.getNextSibling (hItem节点句柄)

返回后面的兄弟节�?
参数:节点句柄

### treeviewObject.getNextVisible(hItem节点句柄)

返回下一个可见节�?
参数:节点句柄

### treeviewObject.getNotifyCustomDraw()

[返回对象:NMTVCUSTOMDRAWObject](#NMTVCUSTOMDRAWObject)

### treeviewObject.getNotifyCustomDraw(code,ptr)

NM\_CUSTOMDRAW通知消息返回NMLVCUSTOMDRAW结构�?
### treeviewObject.getNotifyDispInfo()

[返回对象:TVDISPINFOObject](#TVDISPINFOObject)

### treeviewObject.getNotifyDispInfo(code,ptr)

该函数限用于onnotify通知回调函数�?
code参数为通知�?ptr参数为NMHDR指针

如果NMHDR指针指向TV\_DISPINFO对象则返回该对象,否则返回空�?
### treeviewObject.getNotifyMessage()

[返回对象:NMTREEVIEWObject](#NMTREEVIEWObject)

### treeviewObject.getNotifyMessage(code,ptr)

该函数限用于onnotify通知回调函数�?
code参数为通知�?ptr参数为NMHDR指针

如果code不是大于\_TVN\_FIRST,并小于\_TVN\_LAST的消�?

该函数返回空�?否则返回NMTREEVIEW对象.

### treeviewObject.getParent()

返回父窗�?
### treeviewObject.getParentItem(hItem节点句柄)

返回父节�?
参数:节点句柄

### treeviewObject.getParentItemData(hItem)

返回父节点关联数�?
### treeviewObject.getPos()

返回相对坐标,�?�?
x,y,cx,cy=win.getPos(hwnd)

### treeviewObject.getPrevSibling(hItem节点句柄)

返回前面的兄弟节�?
参数:节点句柄

### treeviewObject.getPrevVisible(hItem节点句柄)

返回上一个可见节�?
参数:节点句柄

### treeviewObject.getRect()

控件区块位置(::RECT结构�?

### treeviewObject.getRect(true)

控件屏幕区块位置(::RECT结构�?

### treeviewObject.getRoot()

返回根节�? TVI\_ROOT )

注意TVI\_ROOT的子节点并没有父节点

### treeviewObject.getSelection()

返回当前选中节点

### treeviewObject.height

高度

### treeviewObject.hide

控件是否隐藏

### treeviewObject.hitTest(x坐标,y坐标,是否屏幕坐标)

该函数返回指定坐标的句柄,参数三可省略,默认为false.

如果不指定任何参�?则自动调�?win.getMessagePos() 获取消息坐标

第二个返回值指定测试结�?该值可以是一个或多个\_TVHT\_开头的常量组合

### treeviewObject.hwnd

控件句柄

### treeviewObject.id

控件ID

### treeviewObject.imageList

获取设置图像列个

支持 win.imageList 对象

### treeviewObject.insertItem("插入文本",父项,前面的子�?

参数@1可以是普通文�?

可使用数组添加多个兄弟节�?使用children成员添加多个子节�?
参数@2指定父项(可省�?,参数@3指定插入位置前面的子�?可省�?

返回新节点句�?示例

var item = winform.treeview.insertItem("子节�?,item)

### treeviewObject.insertItem(插入TVITEM结构�?父项,前面的子�?

参数@1可以是TVITEM结构体或指定部分成员的table对象

参数@1可使用数组添加多个兄弟节�?使用children成员添加多个子节�?
此函数可自动检测非空成员并自动设定相应mask�?
参数@2指定父项(可省�?,参数@3指定插入位置前面的子�?可省�?

返回新节点句�?示例

var item = winform.treeview.insertItem( text = "根目�? )

### treeviewObject.insertItem(数据�?父项,前面的子�?

参数@1可以使用string.xml对象,

或者使用相同结构的普通表对象,

每个节点对象必须指定tagName或text属�?

treeview按text,label,title,name,tagName的顺序确定显示标�?
每个节点可以用数组包含子节点(但节点本身必须指定tagName或text属�?

也可以使用children成员指向一个数组表示多个子节点

参数@2指定父项(可省�?,参数@3指定插入位置前面的子�?可省�?

返回新节点句�?

此用法请参考aardio范例中的treeview控件演示�?
以及fsys.asar下面几个库的treeData函数

### treeviewObject.insertTable

显示表对象中的名值对以及数组

### treeviewObject.insertTable(tab,hParent)

显示表对象中的名值对以及数组,

支持显示嵌套表，表中不应出现循环引用的成�?

可选用hParent指定父节点句�?
### treeviewObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/)

使窗口绘图区无效

### treeviewObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/,0)

使窗口绘图区无效

不刷新背�?
### treeviewObject.isExpanded(hItem)

节点是否展开状�?
### treeviewObject.isExpandedOnce(hItem)

节点是否至少展开过一�?
### treeviewObject.left

左侧坐标

### treeviewObject.modifyStyle(remove,add,swpFlags)

修改窗口样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### treeviewObject.modifyStyleEx(remove,add,swpFlags)

修改窗口扩展样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS\_EX_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS\_EX_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### treeviewObject.onClick

```aardio aardio
treeviewObject.onClick = function(hItem,data){
    /*单击节点触发此事件，
hItem 为当前节点句柄，data 为该节点绑定的自定义数据�?可返�?true 阻止默认处理�?注意在双击后控件自动获取焦点�?/
}

```

### treeviewObject.onDestroy

```aardio aardio
treeviewObject.onDestroy = function(){
    /*窗口销毁前触发*/
}

```

### treeviewObject.onDoubleClick

```aardio aardio
treeviewObject.onDoubleClick = function(hItem,data){
    /*双击节点触发此事件，
hItem 为当前节点句柄，data 为该节点绑定的自定义数据�?可返�?true 阻止默认处理*/
}

```

### treeviewObject.onRightClick

```aardio aardio
treeviewObject.onRightClick = function(hItem,data){
    /*右键点击节点触发此事件，
hItem 为当前节点句柄，data 为该节点绑定的自定义数据*/
}

```

### treeviewObject.onSelChanged

```aardio aardio
treeviewObject.onSelChanged = function(hItem,data,nmTreeView){
    /*改娈当前节点触发此事件，
hItem 为当前节点句柄，data 为该节点绑定的自定义数据�?nmTreeView �?NMTREEVIEW 结构体参�?/
}

```

### treeviewObject.onStateImageChanging

```aardio aardio
treeviewObject.onStateImageChanging = function(hItem,checked,newImgIndex,oldImgIndex){

     /*状态图像（通常指复选框）变更触发此事件�?hItem 为树视图的变更节点句柄�?checked 为是否切换到勾选图像索引，也就�?2�?newImgIndex,oldImgIndex 分别为新旧状态图像索引�?注意勾选操作并不改变当前节点，默认勾选完成会弹回原来的选中节点�?可调�?setSelected 函数选中当前操作的节�?*/
     //选定节点
     winform.treeview.setSelected(hItem);
}

```

### treeviewObject.oncommand

```aardio aardio
treeviewObject.oncommand = function(id,event){
    /*命令事件触发*/
}

```

### treeviewObject.onnotify

```aardio aardio
treeviewObject.onnotify = function(id,code,ptr){
    /*通知事件触发*/
}

```

### treeviewObject.orphanWindow(transparent,hwndBuddy)

创建悬浮窗口,

悬浮窗口仍然显示在原来的位置,

悬浮窗口如影随形的跟随父窗口移动或改变大�?控件原来的固定边距等参数仍然有效

此控件不建议指定参数

### treeviewObject.postMessage(msg,wParam,lParam)

投递窗口消息到消息队列�?
此函数用法请参�?::User32.PostMessage

### treeviewObject.redraw()

刷新

### treeviewObject.right

右侧坐标

### treeviewObject.selDropHiLite(hItem)

选定节点

似拖放操作的目标项目高亮显示

参数指定节点句柄

### treeviewObject.selFirstVisible(hItem)

选定节点并设置到可视区第一�?
参数指定节点句柄

### treeviewObject.sendMessage(msg,wParam,lParam)

发送窗口消�?
此函数用法请参�?::User32.SendMessage

### treeviewObject.setChecked(节点句柄,是否选中)

勾选指定项的复选框

参数@2,默认值是true

### treeviewObject.setFocus()

设置焦点

### treeviewObject.setFont(指定字体)

指定LOGFONT字体对象,或逻辑字体句柄

### treeviewObject.setFont(混入字体属�?

```aardio aardio
treeviewObject.setFont(point=10;name="宋体");

```

### treeviewObject.setImageList( imageList,\_TVSIL )

指定图像列表,

可选使�?_LVSIL_ 前缀常量指定类型

treeview控件不负责销毁图像列表，用户应在控件不再使用图像列表后释放图像列表�?
### treeviewObject.setItem()

更新项节�?参数为TVITEM结构体或指定部分成员的table对象

如果参数未指定节点句�?则取当前选中节点

成功返回true;

此函数可自动检测非空成员并自动设定相应mask�?
### treeviewObject.setItemData(hItem,data)

设置关联数据

data可以是任意对�?
如果添加项时使用的参数是表而不是结构体,默认设置为关联数�?
### treeviewObject.setItemText(节点句柄,文本)

设置节点文本

省略节点参数则取当前选中节点

### treeviewObject.setParent(控件对象)

改变父窗�?
### treeviewObject.setPos(x坐标,y坐标,�?�?插入位置,参数)

调整窗口位置或排�?所有参数可�?
同时指定x,y坐标则移动位�?
同时指定宽高则改变大�?
指定插入位置(句柄或\_HWND前缀常量)则调整Z�?
### treeviewObject.setRect(rc)

设置控件区块位置(::RECT结构�?

### treeviewObject.setRect(rc,true)

设置控件屏幕区块位置(::RECT结构�?

### treeviewObject.setRedraw(false)

禁止重绘

### treeviewObject.setRedraw(true)

恢复重绘

### treeviewObject.setSelected()

不选定任何节点

### treeviewObject.setSelected(hItem)

选定节点

参数指定节点句柄

### treeviewObject.show(true)

显示控件

### treeviewObject.text

控件文本

### treeviewObject.theme

外观主题,例如

winform.button.theme = "Explorer"

winform.button.theme = false

### treeviewObject.threadCallable()

开启此控件的跨线程调用功能

### treeviewObject.toggle(hItem)

折叠的就展开,展开的就折叠

参数为节点句�?省略则取当前选中�?
### treeviewObject.top

顶部坐标

### treeviewObject.translateCommand()

允许转发转发子窗口的命令（\_WM\_COMMAND）与通知（\_WM\_NOTIFY）消息，

避免子窗�?oncommand，onnotify 等回调失效�?
同时会处理子窗口�?\_WM\_CTLCOLORSTATIC 等消息，

以避免部分外观属性失�?
### treeviewObject.update()

重绘invalidate函数指定的区�?
### treeviewObject.valid

窗口是否有效�?
窗口未关闭返�?true �?
窗口已关闭或正在关闭返回 false

### treeviewObject.visibleCount

获取可见项总数

### treeviewObject.width

宽度

### treeviewObject.wndproc

```aardio aardio
treeviewObject.wndproc = function(hwnd,message,wParam,lParam){
    /*窗口消息回调，返回任意非null值阻止默认回�?wndproc重复赋值时追加函数而不是覆盖之前的回调
设为null添除所有消息回调函�?wndproc也可以是一个表,键要为处理的消息,值为对应的消息回调函�?/
}

```

## 全局对象 成员列表

### \_LPSTR\_TEXTCALLBACK

```aardio aardio
topointer(-1)

```

### \_TVI\_FIRST

treeview中表示同级节点中第一个节点的伪句�?
### \_TVI\_LAST

treeview中表示同级节点中最后一个节点的伪句�?
### \_TVI\_ROOT

treeview中表示根节点的伪句柄

### \_TVI\_SORT

```aardio aardio
topointer(-0x0FFFD)/*_TVI_SORT*/

```

## NMTREEVIEWObject 成员列表

### NMTREEVIEWObject.action

```aardio aardio
0;

```

### NMTREEVIEWObject.hdr

[返回对象:nmhdrObject](#nmhdrObject)

### NMTREEVIEWObject.itemNew

[返回对象:tvitemObject](#tvitemObject)

### NMTREEVIEWObject.itemOld

[返回对象:tvitemObject](#tvitemObject)

### NMTREEVIEWObject.ptDrag

[返回对象:pointObject](#pointObject)

## NMTVCUSTOMDRAWObject 成员列表

### NMTVCUSTOMDRAWObject.clrText

文字颜色

### NMTVCUSTOMDRAWObject.clrTextBk

文字背景�?
### NMTVCUSTOMDRAWObject.iLevel

嵌套级别

### NMTVCUSTOMDRAWObject.nmcd.dwDrawStage

绘图状�?
### NMTVCUSTOMDRAWObject.nmcd.dwItemSpec

行序�?
### NMTVCUSTOMDRAWObject.nmcd.hdc

设置句柄

### NMTVCUSTOMDRAWObject.nmcd.hdr

[返回对象:nmhdrObject](#nmhdrObject)

### NMTVCUSTOMDRAWObject.nmcd.lItemlParam

```aardio aardio
lItemlParam

```

### NMTVCUSTOMDRAWObject.nmcd.rc

[返回对象:rectObject](../../../global/_.html#rectObject)

### NMTVCUSTOMDRAWObject.nmcd.uItemState

```aardio aardio
uItemState

```

### NMTVCUSTOMDRAWObject.update()

更新数据

## TVDISPINFOObject 成员列表

### TVDISPINFOObject.hdr

[返回对象:nmhdrObject](#nmhdrObject)

### TVDISPINFOObject.item

[返回对象:tvitemObject](#tvitemObject)

## tvitemObject 成员列表

### tvitemObject.cChildren

子项目数�?
如果�?1则向父窗体发送\_TVN\_GETDISPINFO通知消息

### tvitemObject.cchTextMax

取文本时可在此指定缓冲区长度

### tvitemObject.hItem

节点句柄

### tvitemObject.iImage

项目非选取状态下,要使用的image在图象列表中的索�?
### tvitemObject.iSelectedImage

项目选取状态下,要使用的image在图象列表中的索�?
### tvitemObject.lParam

数�?
### tvitemObject.mask

可使用一个或多个TVIF\_开头的常量组合

以指定当前结构体哪些成员有效

### tvitemObject.state

可使用一个或多上TVIS\_开头的常量组合

### tvitemObject.stateMask

数�?
### tvitemObject.text

文本

### 全局常量

### \_LPSTR\_TEXTCALLBACK

```aardio aardio
topointer(-1)

```

### \_TVI\_FIRST

treeview中表示同级节点中第一个节点的伪句�?
### \_TVI\_LAST

treeview中表示同级节点中最后一个节点的伪句�?
### \_TVI\_ROOT

treeview中表示根节点的伪句柄

### \_TVI\_SORT

```aardio aardio
topointer(-0x0FFFD)/*_TVI_SORT*/

```

### 自动完成常量

\_I\_CHILDRENCALLBACK=-1

\_I\_IMAGECALLBACK=-1

\_TVE\_COLLAPSE=1

\_TVE\_EXPAND=2

\_TVE\_TOGGLE=3

\_TVGN\_CARET=9

\_TVGN\_CHILD=4

\_TVGN\_DROPHILITE=8

\_TVGN\_FIRSTVISIBLE=5

\_TVGN\_LASTVISIBLE=0xA

\_TVGN\_NEXT=1

\_TVGN\_NEXTSELECTED=0xB

\_TVGN\_NEXTVISIBLE=6

\_TVGN\_PARENT=3

\_TVGN\_PREVIOUS=2

\_TVGN\_PREVIOUSVISIBLE=7

\_TVGN\_ROOT=0

\_TVHT\_ABOVE=0x100

\_TVHT\_BELOW=0x200

\_TVHT\_NOWHERE=1

\_TVHT\_ONITEM=0x46

\_TVHT\_ONITEMBUTTON=0x10

\_TVHT\_ONITEMICON=2

\_TVHT\_ONITEMINDENT=8

\_TVHT\_ONITEMLABEL=4

\_TVHT\_ONITEMRIGHT=0x20

\_TVHT\_ONITEMSTATEICON=0x40

\_TVHT\_TOLEFT=0x800

\_TVHT\_TORIGHT=0x400

\_TVIF\_CHILDREN=0x40

\_TVIF\_EXPANDEDIMAGE=0x200

\_TVIF\_HANDLE=0x10

\_TVIF\_IMAGE=2

\_TVIF\_INTEGRAL=0x80

\_TVIF\_PARAM=4

\_TVIF\_SELECTEDIMAGE=0x20

\_TVIF\_STATE=8

\_TVIF\_STATEEX=0x100

\_TVIF\_TEXT=1

\_TVIS\_BOLD=0x10

\_TVIS\_CUT=4

\_TVIS\_DROPHILITED=8

\_TVIS\_EXPANDED=0x20

\_TVIS\_EXPANDEDONCE=0x40

\_TVIS\_EXPANDPARTIAL=0x80

\_TVIS\_EX\_ALL=2

\_TVIS\_EX\_DISABLED=2

\_TVIS\_EX\_FLAT=1

\_TVIS\_OVERLAYMASK=0xF00

\_TVIS\_SELECTED=2

\_TVIS\_STATEIMAGEMASK=0xF000

\_TVIS\_USERMASK=0xF000

\_TVM\_CREATEDRAGIMAGE=0x1112

\_TVM\_DELETEITEM=0x1101

\_TVM\_EDITLABELW=0x1141

\_TVM\_ENDEDITLABELNOW=0x1116

\_TVM\_ENSUREVISIBLE=0x1114

\_TVM\_GETCOUNT=0x1105

\_TVM\_GETIMAGELIST=0x1108

\_TVM\_GETINDENT=0x1106

\_TVM\_GETINSERTMARKCOLOR=0x1126

\_TVM\_GETISEARCHSTRINGA=0x1117

\_TVM\_GETISEARCHSTRINGW=0x1140

\_TVM\_GETITEMHEIGHT=0x111C

\_TVM\_GETITEMRECT=0x1104

\_TVM\_GETITEMSTATE=0x1127

\_TVM\_GETITEMW=0x113E

\_TVM\_GETLINECOLOR=0x1129

\_TVM\_GETNEXTITEM=0x110A

\_TVM\_GETSCROLLTIME=0x1122

\_TVM\_GETTOOLTIPS=0x1119

\_TVM\_GETVISIBLECOUNT=0x1110

\_TVM\_HITTEST=0x1111

\_TVM\_INSERTITEMW=0x1132

\_TVM\_SETIMAGELIST=0x1109

\_TVM\_SETINDENT=0x1107

\_TVM\_SETINSERTMARK=0x111A

\_TVM\_SETINSERTMARKCOLOR=0x1125

\_TVM\_SETITEMHEIGHT=0x111B

\_TVM\_SETITEMW=0x113F

\_TVM\_SETLINECOLOR=0x1128

\_TVM\_SETSCROLLTIME=0x1121

\_TVM\_SETTOOLTIPS=0x1118

\_TVM\_SORTCHILDREN=0x1113

\_TVM\_SORTCHILDRENCB=0x1115

\_TVNRET\_DEFAULT=0

\_TVNRET\_SKIPNEW=2

\_TVNRET\_SKIPOLD=1

\_TVN\_ASYNCDRAW=0xFFFFFE5C

\_TVN\_BEGINDRAGW=0xFFFFFE38

\_TVN\_BEGINLABELEDITW=0xFFFFFE35

\_TVN\_BEGINRDRAGW=0xFFFFFE37

\_TVN\_DELETEITEMW=0xFFFFFE36

\_TVN\_ENDLABELEDITW=0xFFFFFE34

\_TVN\_FIRST=0xFFFFFE70

\_TVN\_GETDISPINFOW=0xFFFFFE3C

\_TVN\_GETINFOTIPW=0xFFFFFE62

\_TVN\_ITEMCHANGEDW=0xFFFFFE5D

\_TVN\_ITEMCHANGINGW=0xFFFFFE5F

\_TVN\_ITEMEXPANDEDW=0xFFFFFE39

\_TVN\_ITEMEXPANDINGW=0xFFFFFE3A

\_TVN\_KEYDOWN=0xFFFFFE64

\_TVN\_LAST=0xFFFFFE0D

\_TVN\_SELCHANGEDW=0xFFFFFE3D

\_TVN\_SELCHANGINGW=0xFFFFFE3E

\_TVN\_SINGLEEXPAND=0xFFFFFE61

\_TVSIL\_NORMAL=0

\_TVSIL\_STATE=2

\_TVSI\_NOSINGLEEXPAND=0x8000

\_TVS\_DISABLEDRAGDROP=0x10

\_TVS\_EX\_AUTOHSCROLL=0x20

\_TVS\_EX\_DIMMEDCHECKBOXES=0x200

\_TVS\_EX\_DOUBLEBUFFER=4

\_TVS\_EX\_DRAWIMAGEASYNC=0x400

\_TVS\_EX\_EXCLUSIONCHECKBOXES=0x100

\_TVS\_EX\_FADEINOUTEXPANDOS=0x40

\_TVS\_EX\_MULTISELECT=2

\_TVS\_EX\_NOINDENTSTATE=8

\_TVS\_EX\_PARTIALCHECKBOXES=0x80

\_TVS\_EX\_RICHTOOLTIP=0x10

\_TVS\_NONEVENHEIGHT=0x4000

\_TVS\_RTLREADING=0x40

\_TVS\_SHOWSELALWAYS=0x20

\_TVS\_TRACKSELECT=0x200

\_TV\_FIRST=0x1100

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/win/ui/ctrl/treeview.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/win/ui/ctrl/treeview.md')

