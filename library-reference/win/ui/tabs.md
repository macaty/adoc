[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# win.ui.tabs 库模块帮助文�?
[高级选项卡使用指南](https://www.aardio.com/zh-cn/doc/library-guide/std/win/ui/tabs/_.md)

## win.ui.tabs 成员列表

高级选项卡（ tab plus ）�?
高级选项卡并不是一个控件，而是用于管理一�?plus 控件�?win.ui.ctrl.plus ）以实现选项卡效果的管理组件�?
创建高级选项卡（ tab plus ）�?
自动查找附近合适的 custom 控件作为页面容器�?
优先选择未禁用、未隐藏、未设置透明�?custom 控件�?
如果是水平选项卡，应在下侧放置 custom 控件作为页面容器,

如果是垂直选项�?应在右侧放置 custom 控件作为页面容器�?
为了避免在启动软件时一次性加载大量子窗口导致启动速度�?

为每一个选项卡添加子窗口时，win.ui.tabs 默认会创建并返回伪窗口�?
直到点击该选项卡或访问伪窗口的属性与方法（fake 属性除外）时才会真正初始化相应的子窗口

### win.ui.tabs.defaultStyle

```aardio aardio
win.ui.tabs.defaultStyle = {
    foreground={
        active=0xFFFFFFFF;
        default=0x00FFFFFF;
        hover=0x38FFFFFF
    };
    color = {
        default=0xFFFFFFFF;
    };
    checked={
        foreground={default=0xFFFFFFFF;};
        color={default=0xFF42A875;};/*默认选项卡样�?/
    }
}

```

### win.ui.tabs.dropButtonStyle

```aardio aardio
win.ui.tabs.dropButtonStyle = {
    color = {
        hover = 0xff99ffcc;
        active = 0xffff6666;
        default = 0xffffffff;
    }/*选项卡下拉按钮默认样�?/
}

```

## win.ui 成员列表

### win.ui.tabs()

[返回对象:winUiTabsObject](#winUiTabsObject)

### win.ui.tabs(headerTab1,headerTab2)

创建高级选项卡�?
参数必须指定至少2个已创建�?plus 控件模板,对象创建成功可选清除模�?
如果不需要动态增删选项�?参数中的 plus 控件无需保持均匀间隔,

动态增加选项卡时会根据模板控件的样式与位�?

自动分析是水平排列还是垂直排�?自动分析排列间距�?
并动态添加选项�?可选显示删除选项卡的按钮

添加的选项卡数目超出显示范围时可自动折叠到下拉菜单�?
自动折叠功能会保证新增选项卡、当前选项卡位于可见位�?

这会导致选项卡在必要时自动调整位�?

所以同一索引并不一定指向同一选项�?
## winUiTabsObject 成员列表

### winUiTabsObject.add(tabConfig)

```aardio aardio
winUiTabsObject.add({
    text="标题文本";
    iconText='\uF0AD';
    foreground="\res\images\icon.png";
    hasCloseButton=true;/*添加选项卡按�?- 使用plus控件创建,
参数@1可以指定部分创建 plus 控件的参�?未指定的参数自动补全,
text字段可用于指定显示文�?foreground 字段可用于指定前景图�?如果指定 hasCloseButton �?true，鼠标悬停会显示关闭按钮,
参数@1也可以使用一个数组指定创建多个选项卡的选项

如果存在多个参数,
自参�?@2 开始作�?loadForm 函数的参数加载窗体并绑定当前选项�?
此函数成功返回新增的选项卡索�?注意如果超出显示范围,
新增选项卡会自动替换到可显示位置*/
})

```

### winUiTabsObject.addItems(options)

参数@option指定一个数组，

遍历数组中的项并作为参数调用add函数创建多个选项�?

参数为null或空数组时忽略不执行任何操作

### winUiTabsObject.adjust()

```aardio aardio
winUiTabsObject.adjust = function(){
    var x,y,cx,cy = owner.getPos();
    /*选项卡已重新调整布局*/
}

```

### winUiTabsObject.adjustLayout()

调整布局

高级选项卡会在需要的时候自动调用此函数

### winUiTabsObject.beforeShowCloseButton(tab,rcTabItem,rcCloseButton,dpiScaleX,dpiScaleY)

```aardio aardio
winUiTabsObject.beforeShowCloseButton = function(tab,rcTab,rcCloseButton){
    /*返回关闭按钮显示的x,y坐标,需要返�?个�?不返回值取消显�?
参数 tab 为请求显示关闭按钮的选项�?rcTab为选项卡所在的区块,::RECT对象,
rcCloseButton为关闭按钮所在的的区�?::RECT对象
dpiScaleX,dpiScaleY为X,Y轴上的DPI缩放比例,1表示100%*/
}

```

### winUiTabsObject.clear()

清空所有选项卡、清空所有加载的子窗�?
### winUiTabsObject.closeButton

选项卡上关闭按钮,plus控件

可调用skin函数自定义外观样�?
可通过beforeShowCloseButton事件自定义显示坐�?
注意这是一个orphanWindow浮动窗口

[返回对象:uiCtrlPlusObject](ctrl/plus.html#uiCtrlPlusObject)

### winUiTabsObject.count()

返回选项卡总数

### winUiTabsObject.create()

[返回对象:uiCtrlPlusObject](ctrl/plus.html#uiCtrlPlusObject)

### winUiTabsObject.create(参数�?

此函数与add函数用法相同

但创建选项卡以后会同时创建对应的子窗口,

返回2个�?分别为创建的选项卡对象、子窗体对象

注意,调用add,create函数添加选项�?

如果超出可见范围,会自动折叠其他选项�?并将新增的选项卡移动到可见位置

所以增加选项卡可能导致选项卡调整位�?索引发生变化

### winUiTabsObject.delete()

删除指定索引的选项�?
参数用数值指定选项所在位置索�?
### winUiTabsObject.deleteByForm()

删除指定的选项�?
参数指定相同索引位置的子窗体对象

### winUiTabsObject.deleteByTab()

删除指定的选项�?
参数指定选项卡按钮对�?
### winUiTabsObject.dropButton

下拉菜单按钮,

如果存在超出显示范围的选项�?这个控件会自动显�?
这是一个plus控件对象

[返回对象:uiCtrlPlusObject](ctrl/plus.html#uiCtrlPlusObject)

### winUiTabsObject.dropButtonMargin

下拉菜单按钮边距

### winUiTabsObject.each()

```aardio aardio
for(tab,form,idx in winUiTabsObject.each() ){
    /*遍历所有选项�?
tab 为选项卡对�?form为对应的子窗�?idx为索引位�?遍历时不应当执行删除、新增选项�?设置当前选项卡等改变索引位置的操�?/
}

```

### winUiTabsObject.getPos()

返回x,y,cx,cy�?个�?

分别表示高级选项卡当前左,上坐�?宽度,高度

### winUiTabsObject.hitTest(x,y)

参数指定屏幕坐标，返回该坐标所在的选项卡，以及选项索引

### winUiTabsObject.indexOfForm()

获取子窗口所在的选项卡索引位�?
参数指定相同索引位置的子窗体对象

### winUiTabsObject.indexOfTab()

获取选项卡所在的索引位置

参数指定选项卡按钮对�?
### winUiTabsObject.initPopup(handleCtrl,transparent)

初始化为弹出菜单样式

@handleCtrl指定接收输入事件的控�?

自动修改该控件的checked属性为是否弹出状�?

transparent指定菜单是否透明,

所有参数可�?
### winUiTabsObject.isVisible()

选项卡是否可�?
### winUiTabsObject.itemMargin

选项卡间隔距�?可以为负�?
### winUiTabsObject.keepSpace

是否保持选项之间的间距不�?

该属性建议由aardio自动设置

### winUiTabsObject.lastVisibleIndex

最后一个显示状态的选项卡索�?
在这后面是因为超出显示范围被自动隐藏的选项�?
### winUiTabsObject.lastVisibleItem

最后一个显示状态的选项�?
在这后面是因为超出显示范围被自动隐藏的选项�?
这是一个plus控件对象

[返回对象:uiCtrlPlusObject](ctrl/plus.html#uiCtrlPlusObject)

### winUiTabsObject.loadForm

加载窗体到高级选项卡的页面容器控件，并绑定选项卡�?
选项卡必须已经匹配到可用的页面容器，

也就是说 panel 属性不为空值�?
高级选项卡默认会自动查找附近合适的 custom 控件作为页面容器

也可以手动指�?panel 指向的窗�?
loadForm 函数默认会加载延迟创建实际窗口的伪窗口�?
访问伪窗口的任何属性或方法都会自动创建真实窗口�?
### winUiTabsObject.loadForm()

在页面容器控件创建默认子窗体并绑定到最后一个选项卡�?
返回创建的子窗口对象�?
### winUiTabsObject.loadForm(index)

在页面容器控件创建默认子窗体并绑定到指定的选项卡�?
�?@index 指定索引，可用负索引表示倒计数，-1 表示最后一个选项卡�?
如果不指定索引则默认�?forms 属性的数组长度并加 1 作为索引�?
与其他函数同的是：此函数省略参数 @1 可不用占位，允许参数 @2 写为 参数 @1�?
省略参数 @2 则立即创建默认子窗体并加载到页面，然后返回该窗体�?
### winUiTabsObject.loadForm(index,"请输入窗体代码文件路�?)

在页面容器控件内预加载创建子窗体的代码文件，

并绑定到参数 @index 指定索引的选项卡�?
参数 @index 可用负索引表示倒计数，-1 表示最后一个选项卡�?
在开发环境中,请注意保存外部窗体文件以后测试运行�?
默认会创建并返回一个伪窗口对象�?
并延迟到用户切换到所属选项卡时才会真正创建窗口�?
访问伪窗口除 fake 以外的任何属性方法也会立即创建窗口�?
### winUiTabsObject.loadForm(index,@tParam)

在页面容器控件内创建子窗体并绑定到参数@1指定索引的选项卡�?
参数 @index 可用负索引表示倒计数，-1 表示最后一个选项卡�?
默认会创建并返回一个伪窗口对象�?
并延迟到用户切换到所属选项卡时才会真正创建窗口�?
访问伪窗口除 fake 以外的任何属性方法也会立即创建窗口�?
### winUiTabsObject.loadForm(index,winform)

�?@winform 指定的子窗体添加到页面容器，

并绑定到参数 @index 指定索引的选项卡�?
参数 @index 可用负索引表示倒计数，-1 表示最后一个选项卡�?
如果不指定索引（可省略参数占位）则默认取 forms 属性的数组长度并加 1 作为索引�?
返回参数 @2 指定的窗体对象�?
### winUiTabsObject.margin

可设置选项卡按钮尾部最少预留的边距,

超出显示范围时自动折叠选项卡并在此显示下拉菜单�?
默认会根据下拉按钮的大小自动设置此�?

如果设置�?则禁用自动折叠功能�?
此属性应设置为系�?DPI 缩放前的原始�?
### winUiTabsObject.next()

切换到下一�?
### winUiTabsObject.onCancel()

```aardio aardio
winUiTabsObject.onCancel = function(){
    /*用户关闭弹出列表﻿并且未确认选项*/
}

```

### winUiTabsObject.onDrawEnd

```aardio aardio
winUiTabsObject.onDrawEnd = function(graphics,rc){
    /*所有绘制操作结束触发此事件,
graphics 为gdip.graphics对象(GDI+画板),
rc为客户区RECT结构�?/
}

```

### winUiTabsObject.onDrawForegroundEnd

```aardio aardio
winUiTabsObject.onDrawForegroundEnd = function(graphics,rc,rcContent){
    /*背景前景绘制�?绘制文本前触发此事件,
graphics 为gdip.graphics对象(GDI+画板),
rc为客户区RECT结构�?rcContent为去掉内边距后的RECT结构�?/
}

```

### winUiTabsObject.onDrawString(...)

```aardio aardio
winUiTabsObject.onDrawString(...onDrawString = function(graphics,text,font,rectf,strformat,brush){
    graphics.drawString(text,font,rectf,strformat,brush);
    /*自绘所有选项卡控钮上的文�?注意owner参数指向当前选项卡按�?/
}

```

### winUiTabsObject.onFocusGot(hLostFocus)

```aardio aardio
winUiTabsObject.onFocusGot = function(hLostFocus){
    ..win.setFocus(hLostFocus);/*得到焦点触发此事�?hLostFocus为失去焦点的窗口句柄*/
}

```

### winUiTabsObject.onFocusLost(hFocus)

```aardio aardio
winUiTabsObject.onFocusLost = function(hFocus){
    /*失去焦点触发此事�?hFocus为得到焦点的窗口句柄*/
}

```

### winUiTabsObject.onMouseDown(tab,wParam,lParam)

```aardio aardio
winUiTabsObject.onMouseDown = function(tab,wParam,lParam){
    /*在选项卡对�?tab 上按下鼠�?即将切换当前选项�?
wParam,lParam为窗口消息参�?/
}

```

### winUiTabsObject.onMouseHover(tab,wParam,lParam)

```aardio aardio
winUiTabsObject.onMouseHover = function(tab,wParam,lParam){
    /*鼠标正悬浮于选项卡对�?tab 之上,
wParam,lParam为窗口消息参�?/
}

```

### winUiTabsObject.onMouseLeave(tab,wParam,lParam)

```aardio aardio
winUiTabsObject.onMouseLeave = function(tab,wParam,lParam){
    /*鼠标离开选项卡对�?tab,
wParam,lParam为窗口消息参�?/
}

```

```aardio aardio
winUiTabsObject.onMouseLeave = function(tab,wParam,lParam){
    /*鼠标离开选项卡对�?tab,
wParam,lParam为窗口消息参�?/
}

```

### winUiTabsObject.onMouseUp(tab,wParam,lParam)

```aardio aardio
winUiTabsObject.onMouseUp = function(tab,wParam,lParam){
    /*在选项卡对�?tab 上放开鼠标,选项卡切换操作已完成,
wParam,lParam为窗口消息参�?/
}

```

### winUiTabsObject.onOk(tab)

```aardio aardio
winUiTabsObject.onOk = function(tab){
    /*用户在弹出列表中选择并确认选项,且即将关闭弹出列�?/
}

```

### winUiTabsObject.onPopup(showing)

```aardio aardio
winUiTabsObject.onPopup = function(showing){
    /*弹出状态变更时触发此事�?弹出状态@showing参数为true，显示为弹出状态@showing参数为false*/
}

```

### winUiTabsObject.onSelchange(idx,tab,form)

```aardio aardio
winUiTabsObject.onSelchange = function(idx,tab,form){
    /*切换选项卡会触发此事�?idx为当前选中索引
tab 为当前选项�?form为当前子窗口*/
}

```

### winUiTabsObject.onVisualStateChanged(showing)

```aardio aardio
winUiTabsObject.onVisualStateChanged = function(showing){
    /*显示或隐藏时触发此事�?显示@showing参数为true，隐藏@showing参数为false*/
}

```

### winUiTabsObject.oncommand(tab,id,event)

```aardio aardio
winUiTabsObject.oncommand = function(tab,id,event){
    /*点击选项卡触发此函数
tab 为触发事件的选项�?id为控件id,event目前值总是0*/
}

```

### winUiTabsObject.panel

用于构成选项卡内容区域（ tab body area ）的容器控件�?
必须是一�?custom 控件（win.ui.ctrl.custom 控件）�?
创建高级选项卡时，panel 属性会自动指定为附近可用的 custom 控件�?
也可以在加载子窗口以前手工指定此对象

[返回对象:winform](_.html#winform)

### winUiTabsObject.popup

切换到弹出列表模式，

用于显示简单的弹出列表或菜单，

如果当前项目列表数组为空,则无论传入什么参数都会切换到隐藏状�?
### winUiTabsObject.popup(false)

隐藏列表，并将selIndex置为null

如果当前项目列表数组为空,则无论传入什么参数都会切换到隐藏状�?
### winUiTabsObject.popup(true,ctrl,mode)

弹出列表

ctrl指定控件，弹出列表显示在该控件边�?

自动修改该控件的checked属性为是否弹出状�?

可选使用mode参数指定"up","down","left","right"等显示位�?
### winUiTabsObject.popup(true,x,y)

弹出列表

可选使用x,y指定列表左上角在屏幕上的坐标

### winUiTabsObject.prev()

切换到上一�?
### winUiTabsObject.query()

[返回对象:winform](_.html#winform)

### winUiTabsObject.query(查询属�?

```aardio aardio
winUiTabsObject.query(
    text = "标题";
    tabsName = "名字";/*使用选项卡的指定属性查询对应的子窗�?
如果子窗口没有加载将会立即加�?
选项卡的任一属性值与查询条件相同即可
自定义属性建议加上tabs前缀以避免冲�?也可以用一个字符串参数直接查询选项卡标�?
返回窗口对象,以及所在索�?/
)

```

### winUiTabsObject.queryTab()

[返回对象:uiCtrlPlusObject](ctrl/plus.html#uiCtrlPlusObject)

### winUiTabsObject.queryTab(查询属�?

```aardio aardio
winUiTabsObject.queryTab(text = "标题"/*使用选项卡的指定属性查询对应的选项�?
选项卡的任一属性值与查询条件相同即可
自定义属性建议加上tabs前缀以避免冲�?也可以用一个字符串参数直接查询选项卡标�?
返回选项卡对�?以及所在索�?/)

```

### winUiTabsObject.selForm

当前选中的子窗口

[返回对象:winform](_.html#winform)

### winUiTabsObject.selIndex

获取或指定当前选中项索�?设为null清除当前选项,

如果新的选中项已被自动折�?则会自动移动到可见位�?
所以设置selIndex时可能导致selIndex移动位置

### winUiTabsObject.selTab

获取或指定当前选中的选项卡按�?
指定null或不存在于tabs中的控件时清除选中�?

[返回对象:uiCtrlPlusObject](ctrl/plus.html#uiCtrlPlusObject)

### winUiTabsObject.selText

获取当前选中项文�?

也可以指定一个文本用于切换到显示该文本的选项�?
### winUiTabsObject.setItemTexts

使用文本数组更新选项卡数�?

此函数可重用已创建的选项卡，所以有更好的性能

### winUiTabsObject.setItemTexts(texts,limit,selIndex)

使用参数@texts指定的字符串数组创建选项卡数�?

其中的每个字符串用于指定选项卡上的显示文本�?
可选用@limit参数指定最大显示条�?

可选用@selIndex参数指定默认选中索引,

此函数返回实际显示条�?
### winUiTabsObject.setItems

使用控件初始化选项数组更新选项卡数�?

此函数可重用已创建的选项卡，所以有更好的性能

### winUiTabsObject.setItems(items,limit,selIndex)

使用参数@items指定的选项数组更新选项卡数�?

每个选项提供控件的初始化属性并将被传入add函数�?
可选用@limit参数指定最大显示条�?

可选用@selIndex参数指定默认选中索引,

此函数返回实际显示条�?
### winUiTabsObject.setTabs(属性名,属性值数�?

设置所有选项卡的指定属性�?
### winUiTabsObject.show(可选输入显示参�?

显示或隐藏所有选项�?可选输入以\_SW\_为前缀的显示参�?
参数@1也可以传入true,false控制是否显示选项�?
### winUiTabsObject.showDropButton(true)

参数为true显示下拉菜单按钮

参数为false隐式该按�?
高级选项卡会在需要的时候自动调用此函数

### winUiTabsObject.skin

```aardio aardio
winUiTabsObject.skin({
    background = {
        hover = "/res/images/button-hover.png";
        focus = "/res/images/button-focus.png";
        active = "/res/images/button-active.png";
        disabled = 0xFFCCCCCC;
    };
    color = {
        hover = 0xF00000FF;/*用格式为0xAARRGGBB�?6进制数�?指定鼠标放到控件上的字体颜色,
AA为透明�?RR为红色分�?GG为绿色分�?BB为蓝色分�?/
    };
    border = {
        hover = {left=5;color=0xFFFF0000;padding=15;}
    };
})

```

### winUiTabsObject.swap(a,b)

交换两个索引的选项卡位�?
参数a,b应当是有效的选项卡索�?
这个函数如果没有弄清楚原理最好不要使�?

高级选项卡会在需要的时候自动调用此函数,

成功返回true,失败返回null

### winUiTabsObject.updateItemRegion()

更新选项卡绘图区�?

参数必须是兼�?win.region.png 接口的对�?
## winUiTabsObject.forms 成员列表

用于显示页面内容的子窗口数组�?
选中的子窗口将在 panel 属性指定的容器控件中显示�?
### winUiTabsObject.forms.?

子窗口是 win.form 对象

[返回对象:winform](_.html#winform)

## winUiTabsObject.tabList 成员列表

用于构成选项卡头部区域（ tab header area ）的选项卡按钮数组�?
所有选项卡按钮都�?plus 控件（win.ui.ctrl.plus 控件）�?
### winUiTabsObject.tabList.?

选项卡按钮数组包含的按钮对象�?
所有选项卡按钮都�?plus 控件（win.ui.ctrl.plus 控件）�?
[返回对象:uiCtrlPlusObject](ctrl/plus.html#uiCtrlPlusObject)

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/win/ui/tabs.md)

