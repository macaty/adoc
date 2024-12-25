[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# win.ui.ctrl.plus 库模块帮助文�?
## win.ui.ctrl 成员列表

### win.ui.ctrl.plus

高级图像控件

### win.ui.ctrl.plus()

高级图像控件

[返回对象:uiCtrlPlusObject](plus.html#uiCtrlPlusObject)

## uiCtrlPlusObject 成员列表

### uiCtrlPlusObject.\_embedObject

嵌入 COM 控件的容器对�?
[返回对象:embedObject](../../../com/_.html#embedObject)

### uiCtrlPlusObject.\_parentForm

控件所在的父窗�?指win.form对象)

[返回对象:winform](../_.html#winform)

### uiCtrlPlusObject.addCtrl

```aardio aardio
uiCtrlPlusObject.addCtrl(
    button={ cls="button";text="button";left=33;top=32;right=126;bottom=81;autoResize=false }
)

```

### uiCtrlPlusObject.adjust

```aardio aardio
uiCtrlPlusObject.adjust = function( cx,cy,wParam ) {
    /*窗口缩放时会自动触发此函数�?cx 参数为窗口宽�?cy 参数为窗口高�?
wParam 参数请参�?_WM_SIZE 消息参数说明,一般不用管�?
所�?win.form 创建的窗体和控件都支持此事件,
重复赋值只会追加而不会覆盖此事件�?一般不建议添加一�?wndproc 仅仅是为了处�? _WM_SIZE 消息�?定义 adjust 事件是更好的选择�?
可主动调用此事件,省略参数�?cx,cy 参数默认设为窗口大小*/
};

```

### uiCtrlPlusObject.align

文本水平对齐,

左对齐："left"

居中�?center"

右对齐："right"

图标文本请使�?iconStyle 属性的 align 字段指定水平对齐

### uiCtrlPlusObject.animation

是否允许自动播放 GIF 动画�?
指定�?false 禁止自动播放

### uiCtrlPlusObject.animationId

动画定时器ID

不可改动，可用于判断动画是否启动

### uiCtrlPlusObject.animationState

此属性表示动画当前状态�?值null或false表示动画已停�?
### uiCtrlPlusObject.argbColor

ARGB格式字体颜色,支持半透明

注意plus控件、GDI+都是ARGB格式数值表示颜色分�?�?0xAARRGGBB

与RGB的分量顺序是反过来的

### uiCtrlPlusObject.autoResize

是否允许跟随父窗体自动缩�?
### uiCtrlPlusObject.background

背景图像或背景色,

获取值是返回 gdip.bitmap 对象�?ARGB 格式颜色数值，

赋值时可指定图像路径、资源路径、gdip.bitmap 对象、颜色值，

颜色值使�?xAARRGGBB格式的数值�?
赋值时指定一个路径或资源路径控件将自动缓存使用频繁的图像

内存图像建议使用setBackground函数指定缓存�?
[返回对象:gdipbitmapObject](https://www.aardio.com/zh-cn/doc/library-reference/gdip/bitmap.html#gdipbitmapObject)

### uiCtrlPlusObject.backgroundColor

当前状态背景颜�?

修改背景色建议设�?background 属性为数值即可，

直接修改 backgroundColor 不会释放之前的背景图像且不会重绘

### uiCtrlPlusObject.bkBottom

背景图expand模式下九宫格切图的底部切�?
### uiCtrlPlusObject.bkLeft

背景图expand模式下九宫格切图的左侧切�?
### uiCtrlPlusObject.bkRight

背景图expand模式下九宫格切图的右侧切�?
如果控件显示为水平滑块控�?此属性用于预留滑块按钮大�?
### uiCtrlPlusObject.bkTop

背景图expand模式下九宫格切图的顶部切�?
### uiCtrlPlusObject.border

```aardio aardio
uiCtrlPlusObject.border = {color=0x805F9EA0;radius=11;width=2}/*使用一个表对象指定当前边框样式�?支持的字段请参考窗体设计器中设置边框样式生成的代码�?表的其他可用字段�?skin 函数指定�?border 样式相同，请参考范例�?修改此属性不会触发重绘�?可使�?predraw �?redraw,redrawTransparent 等函数重�?/

```

### uiCtrlPlusObject.bottom

底部坐标

### uiCtrlPlusObject.capture

是否捕获全局鼠标消息

### uiCtrlPlusObject.changeInterval(定时器ID,间隔时间,回调函数)

重新设置间隔时间或回调函�?
### uiCtrlPlusObject.checked

该属性可用于切换选取状�?
### uiCtrlPlusObject.className

运行时类�?
### uiCtrlPlusObject.clearInterval(定时器ID)

删除定时器�?
参数如果�?null 则忽略不执行�?
否则定时器ID必须�?setInterval 函数或setTimeout函数的返回值�?
请注意如果定时器被删除，ID 可能被重新分配给其他定时器�?
在定时器回调函数中返�?0,false 以删除定时器是更稳妥的方�?
### uiCtrlPlusObject.clearTimeout(定时器ID)

删除定时器�?
参数如果�?null 则忽略不执行�?
否则定时器ID必须�?setInterval 函数或setTimeout�?数的返回值�?
请注意如果定时器被删除，ID 可能被重新分配给其他定时器�?
在定时器回调函数中返�?0,false 以删除定时器是更稳妥的方�?
### uiCtrlPlusObject.close()

关闭控件窗口

### uiCtrlPlusObject.cls

设计时类�?
### uiCtrlPlusObject.color

RGB格式字体颜色,

如果启用了编辑模�?可同步修改编辑框字体颜色,

注意使用argbColor修改颜色不能同步修改编辑框颜�?
### uiCtrlPlusObject.createEditBox(创建控件参数)

```aardio aardio
uiCtrlPlusObject.createEditBox(
    vscroll = true;
    hscroll = true;
    multiline = true;
);/*创建并启用透明背景的richedit文本编辑框，可用参数与窗体设计器相同�?创建文本框时应用plus控件预设的字体、颜色、水平对齐方式，
并且使用plus控件预设的内边距限制文本编辑框显示范围�?
可使用editBox属性访问此文本编辑框，
可通过设置plus控件的editable属性显示或隐藏文本编辑�?/

```

### uiCtrlPlusObject.createEmbed

创建嵌入控件,返回控件容器对象,

容器对象�?\_object 成员是创建的 COM 对象,

容器对象可通过添加成员函数响应 COM 对象事件�?
容器对象的主要作用是充当访问 COM 对象的中间代理对象�?
通常使用 util.metaProperty 为容器对象添加属性元表，

属性元表可拦截属性、函数调用并调用 \_object 对象,

createEmbedEx 返回的容器已添加默认代理以直接访�?COM 对象

### uiCtrlPlusObject.createEmbed()

[返回对象:embedObject](../../../com/_.html#embedObject)

### uiCtrlPlusObject.createEmbed(clsId,embedObj)

创建嵌入控件,返回控件容器对象,

容器对象�?\_object 成员是创建的 COM 对象,

容器对象可通过添加成员函数响应 COM 对象事件�?
容器对象的主要作用是充当访问 COM 对象的中间代理对�?

@clsId 指定控件 CLSID,

可选在参数@2中指�?COM 对象绑定的容器对�?
此函数失败会抛出异常

### uiCtrlPlusObject.createEmbed(comObject,embedObj)

嵌入 COM 控件,返回控件容器对象,

容器对象�?\_object 成员是传入的 COM 对象,

容器对象可通过添加成员函数响应 COM 对象事件�?
容器对象的主要作用是充当访问 COM 对象的中间代理对�?

@comObject 指定已创建成功的 COM 对象,

可选在参数@2中指�?COM 对象绑定的容器对�?
此函数失败会抛出异常

### uiCtrlPlusObject.createEmbedEx

创建嵌入控件,返回控件容器对象,

容器对象�?\_object 成员是创建的 COM 对象,

容器对象可通过添加成员函数响应 COM 对象事件�?
容器对象的主要作用是充当访问 COM 对象的中间代理对象�?
此函数返回的容器已添加元表并创建代理以直接访�?COM 对象

### uiCtrlPlusObject.createEmbedEx()

[返回对象:embedObject](../../../com/_.html#embedObject)

### uiCtrlPlusObject.createEmbedEx(clsId,embedObj)

创建嵌入控件,返回控件容器对象,

此函数返回的容器已添加元表并创建代理以直接访�?COM 对象,

@clsId 指定控件 CLSID,如果控件不是自内存加�?

则可省略 @clsId 并由 firstCoClassId函数自动�?

可选在参数@2中指�?COM 对象绑定的容器对�?
此函数失败会抛出异常

### uiCtrlPlusObject.directDrawBackgroundOnly()

允许直接在背景窗口上画图

并禁止控件在自己的窗口绘�?
### uiCtrlPlusObject.disablePaint()

禁用默认绘图操作

### uiCtrlPlusObject.disabled

是否禁用

### uiCtrlPlusObject.disabledText

```aardio aardio
uiCtrlPlusObject.disabledText = {'\uF254';'\uF251';'\uF252';'\uF253';'\uF250';text=''}/*指定文本�?禁用此控�?并显示指定文�?
指定一个数组时,控件将创建动画逐帧显示数组里的文字图标,
如果控件配置了iconStyle属�?则使用iconText属性显示数组内的文字图�?
指定为null�?启用此控�?并恢复控件禁用之前的text、iconText属�?/

```

### uiCtrlPlusObject.dpiScale(x,y)

�?@x,@y 表示的像素值乘以窗体当�?DPI 缩放倍数并返�?

省略 @y 参数时仅返回 @x 转换后的�?
### uiCtrlPlusObject.dpiScaleX

窗口当前使用的DPI横坐标缩放系�?

该值由界面系统自动维护，任何情况下都不应手动修�?

这是一个以小数表示百分比的数，例如 1.25 表示 125%,

窗口未使用缩放或未完成缩放初始化时，值可能为 null�?
如果要获取屏幕缩放设置应改用 gdi.getDpiScale 函数

### uiCtrlPlusObject.dpiScaleY

窗口当前使用的DPI纵坐标缩放系�?

该值由界面系统自动维护，任何情况下都不应手动修�?

这是一个以小数表示百分比的数，例如 1.25 表示 125%,

窗口未使用缩放或未完成缩放初始化时，值可能为 null�?
如果要获取屏幕缩放设置应改用 gdi.getDpiScale 函数

### uiCtrlPlusObject.drawToDevice(hdc,x,y)

输出控件图像到hdc参数指定的GDI绘图设备,

x,y为输出坐�?如果绘图到父窗口,x,y参数可省�?
### uiCtrlPlusObject.drawToGraphics(graphics,x,y)

输出控件图像到hdc参数指定的GDI+画板,

x,y为输出坐�?如果绘图到父窗口,x,y参数可省�?
### uiCtrlPlusObject.editBox

文本编辑�?此文本框也是一个win.ui.tracker对象,

[返回对象:richeditObject](#richeditObject)

### uiCtrlPlusObject.editState

允许共享内部编辑框的外观状�?不指定默认值为true,

如果希望利用文本边距、前景边距等模拟分离按钮

可将此值显示指定为false

### uiCtrlPlusObject.editable

是否允许编辑文本

如果此值设为true则切换到可编辑模�?

也可以指定要嵌入的编辑框的类名，例如"edit",

不指定类名则创建透明背景的richedit文本编辑�?
在首次切换到可编辑模式下创建文本框，

并同步应用plus控件预设的字体、颜色、水平对齐方式，

并使用plus控件预设的内边距限制文本编辑框显示范围�?
可使用editBox属性访问此文本编辑框，

如果文本编辑框已创建，再次修改editable仅显示或隐藏文本编辑�?
### uiCtrlPlusObject.enableDpiScaling(false)

禁用DPI自动缩放,

不指定参数启用DPI自动缩放,默认已启�?
### uiCtrlPlusObject.fitContent ()

控件调整大小调整到适应当前显示字数

### uiCtrlPlusObject.focusOnClick

设为false时禁止在单击控件时设置此控件为焦点控�?
### uiCtrlPlusObject.font

控件字体（LOGFONT 结构体）�?
注意获取该属性总是返回新的 LOGFONT 对象�?
修改返回字体并不会更新控件字体，

除非重新赋值�?
建议尽量优先使用 getFont �?setFont 函数�?
以增强代码可读�?
字体会根据控件设置自动处�?DPI 缩放，不需要事先缩放字体大�?
### uiCtrlPlusObject.fontCharMap

指定自定义字符映射表,

键为字符,值为用于显示字符的gdip.bitmap对象

如果指定了此属性则忽略字体大小,使用textPadding以及内边距限制输出大�?
### uiCtrlPlusObject.foreBottom

前景图expand模式下九宫格切图的底部切�?
### uiCtrlPlusObject.foreLeft

前景图expand模式下九宫格切图的左侧切�?
### uiCtrlPlusObject.foreRepeat

前景显示模式

支持模式expand,stretch,center,tile,scale

如果为null则foreLeft,foreRight为偏移坐标\\expand模式foreTop,foreRight,foreBottom,foreLeft为九宫格切图坐标

其他模式为显示边�?
### uiCtrlPlusObject.foreRight

前景图expand模式下九宫格切图的右侧切�?
### uiCtrlPlusObject.foreTop

前景图expand模式下九宫格切图的顶部切�?
如果控件显示为垂直滑块控�?此属性用于预留滑块按钮大�?
### uiCtrlPlusObject.foreground

前景图像或前景色,

获取值是返回 gdip.bitmap 对象�?ARGB 格式颜色数值，

赋值时可指定图像路径、资源路径、gdip.bitmap 对象、颜色值，

颜色值使�?xAARRGGBB格式的数值�?
赋值时指定一个路径或资源路径控件将自动缓存使用频繁的图像

内存图像建议使用setForeground函数指定缓存�?
如果边框圆角设为-1,前景图或前景色会裁剪为圆形后输出,

[返回对象:gdipbitmapObject](https://www.aardio.com/zh-cn/doc/library-reference/gdip/bitmap.html#gdipbitmapObject)

### uiCtrlPlusObject.foregroundColor

当前状态前景颜�?

修改背景色建议设�?foreground 属性为数值即可，

直接修改 foregroundColor 不会释放之前的前景图像且不会重绘

### uiCtrlPlusObject.getBackground()

返回背景图像,返回值为gdip.bitmap对象

此函数不会返回背景色，仅返回背景图像,

如果不存在背景图像返回null

[返回对象:gdipbitmapObject](https://www.aardio.com/zh-cn/doc/library-reference/gdip/bitmap.html#gdipbitmapObject)

### uiCtrlPlusObject.getClientRect()

控件客户区块位置(::RECT结构�?

[返回对象:rectObject](../../../global/_.html#rectObject)

### uiCtrlPlusObject.getFont()

返回控件 LOGFONT 字体�?
返回对象�?h 值会按控件的 DPI 缩放设置自动还原为缩放前大小�?
[返回对象:logfontObject](#logfontObject)

### uiCtrlPlusObject.getFont(true)

返回控件 LOGFONT 字体�?
返回对象�?h 值为字体实际大小，不会按控件 DPI 设置还原�?
返回字体会设�?noScale 属性为 true,

使用控件�?setFont 函数或赋�?font 属性时�?
noScale 属性为 true 的字体同样不会进行自�?DPI 缩放

[返回对象:logfontObject](#logfontObject)

### uiCtrlPlusObject.getFontEx()

返回gdip.font字体

注意字体生命期由控件管理

[返回对象:gdipfontObject](https://www.aardio.com/zh-cn/doc/library-reference/gdip/font.html#gdipfontObject)

### uiCtrlPlusObject.getForeground()

返回前景图像,返回值为gdip.bitmap对象

此函数不会返回前景色，仅返回前景图像,

如果不存在前景图像返回null

[返回对象:gdipbitmapObject](https://www.aardio.com/zh-cn/doc/library-reference/gdip/bitmap.html#gdipbitmapObject)

### uiCtrlPlusObject.getForm()

如果是窗体返回自�?
如果是控件则返回\_parentForm

[返回对象:winform](../_.html#winform)

标准库中所有控件都拥有此同名函数用于返回控件所在窗�?

窗口对象实现了同名函数用于返回窗口自�?
### uiCtrlPlusObject.getParent()

返回父窗�?
### uiCtrlPlusObject.getPos()

返回相对父窗口客户区的坐�?�?�?

参数为true返回屏幕坐标,�?�?

x,y,cx,cy=win.getPos(hwnd)

### uiCtrlPlusObject.getProgressRange()

返回进度条最小�?最大�?
### uiCtrlPlusObject.getRect()

控件区块位置(::RECT结构�?

### uiCtrlPlusObject.getRect(true)

控件屏幕区块位置(::RECT结构�?

### uiCtrlPlusObject.getRoot()

获取顶层父窗口，这个函数会查�?orphanWindow 的父窗口

### uiCtrlPlusObject.height

高度

### uiCtrlPlusObject.hide

当前控件窗口是否隐藏�?
仅检查当前窗口的可见性样式（窗口 是否移除�?\_WS\_VISIBLE 样式）�?
不考虑父窗口是否可见，不考虑是否被其他窗口遮挡�?
如果需要同时判断父窗口的可见性，应改�?win.isVisible 函数�?
### uiCtrlPlusObject.hotkeyPrefix

```aardio aardio
uiCtrlPlusObject.hotkeyPrefix = _GdipHotkeyPrefixShow;

```

### uiCtrlPlusObject.hwnd

控件句柄

### uiCtrlPlusObject.iconColor

字体图标颜色,支持半透明,

支持使用skin函数动态切换此样﻿�?

此颜色存储为ARGB格式，即:0xAARRGGBB,注意在创建控件的初始化参数中必须传入RGB格式颜色�?

请注意在未指定指属性时,图标字体默认与字体使用相同的颜色

### uiCtrlPlusObject.iconFont

图标字体，LOGFONT 结构体�?
获取值时，如果存�?iconStyle.font，直接返�?iconStyle.font�?
�?iconFont 赋值总是会创建新�?LOGFONT 结构并存�?iconStyle.font

使用 iconFont 赋值时可以传入仅指�?LOGFONT 部分成员的普通表�?
修改返回字体的成员不会更�?plus 控件实际使用�?GDI+ 字体�?
只有重新�?iconFont 赋�?，才会在下次重绘时刷�?GDI+ 字体

图标字体会根据控件设置自动处�?DPI 缩放，不需要事先缩放字体大�?
[返回对象:logfontObject](#logfontObject)

### uiCtrlPlusObject.iconStyle

```aardio aardio
uiCtrlPlusObject.iconStyle = {
    font=LOGFONT(h=-38;name='FontAwesome');
    align="left";valign="top";padding={bottom=50}/*用于指定 iconText 显示样式

�?font 指向控件已使用的 iconStyle.font，则控件不会刷新字体�?font 如不�?::LOGFONT 字体，控件将自动转换�?::LOGFONT 字体�?�?iconFont 属性赋值以修改 iconStyle.font 则总是会刷新字�?/
}

```

### uiCtrlPlusObject.iconText

指定文本图标

使用iconStyle指定字体与样�?
### uiCtrlPlusObject.iconTextRenderingHint

```aardio aardio
uiCtrlPlusObject.iconTextRenderingHint = _GdipTextRenderingHint;

```

### uiCtrlPlusObject.id

控件ID

### uiCtrlPlusObject.imageAttributes

可选使用一个gdip.imageAttributes对象对前景图像进行自动调�?
如果需要在不同状态下调色,可以在onStateChange事件里动态设置调色矩�?
[返回对象:gdipImgattrObject](#gdipImgattrObject)

### uiCtrlPlusObject.interpolationMode

图像缩放时的默认插值模�?

默认值为\_GdipInterpolationModeHighQualityBicubic

### uiCtrlPlusObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/)

使窗口绘图区无效

### uiCtrlPlusObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/,0)

使窗口绘图区无效

不刷新背�?
### uiCtrlPlusObject.isDialogMessage

```aardio aardio
uiCtrlPlusObject.isDialogMessage = function(hParent,msg){/*在控件范围内替代父窗口的 isDialogMessage�?可用于在控件范围内屏蔽对话框快捷�?/}

```

### uiCtrlPlusObject.isForm

标准库中所有控件以及窗体对象都拥有此同名函�?
窗体返回true,控件返回false

### uiCtrlPlusObject.isHyperlink()

控件不设置背景、前�?
但设置了显示文本,并启用事件回调则该值返回真

### uiCtrlPlusObject.left

左侧坐标

### uiCtrlPlusObject.linearGradient

数�?指定背景色线性渐变的角度,

渐变从背色颜色开�?到前景颜色结�?
只有背景、前景都指定了当前状态下的颜色值才有效,

270,90为垂直方向的渐变

180,360为水平方向的渐变

此属性指定为负数启用圆形径向渐变,此时background为中心颜色，foreground为环绕颜�?
### uiCtrlPlusObject.measureString()

返回文本输出后的区出大小,返回值为RECTF对象

可选在参数中指定要输出的文�?不指定则取当前显示文�?

[返回对象:rectfObject](https://www.aardio.com/zh-cn/doc/library-reference/gdip/core.html#rectfObject)

### uiCtrlPlusObject.messageOnly()

将窗口转换为message-only window

该窗口不可见,仅用于消息分�?
### uiCtrlPlusObject.modifyStyle(remove,add,swpFlags)

修改窗口样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### uiCtrlPlusObject.modifyStyleEx(remove,add,swpFlags)

修改窗口扩展样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS\_EX_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS\_EX_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### uiCtrlPlusObject.notify

是否启用事件回调

设为false将不能响应鼠标按键等交互事件

### uiCtrlPlusObject.onAnimation(state,beginning,change,timestamp)

```aardio aardio
uiCtrlPlusObject.onAnimation = function(state,beginning,change,timestamp){
    /*动画触发此函�?state 参数是上次返回的�?可以使用plus控件的animationState属性获取这里的返回�?
beginning,change为调用startAnimation指定的参�?
timestamp 参数为动画已执行的时�?
返回值为false或null停止动画*/
    return state
}

```

### uiCtrlPlusObject.onDrawBackground

```aardio aardio
uiCtrlPlusObject.onDrawBackground = function(graphics,rc,bkColor,foreColor){
    /*自绘背景,
graphics 为gdip.graphics对象(GDI+画板),
rc为绘图区�?
bkColor为当前状态背景色,AGGB格式,可能为null
foreColor为当前状态前景色,ARGB格式,不会出现null�?返回真取消默认的背景绘图*/
}

```

### uiCtrlPlusObject.onDrawContent

```aardio aardio
uiCtrlPlusObject.onDrawContent = function(graphics,rc,txtColor,rcContent,foreColor){
    /*自绘前景,
graphics 为gdip.graphics对象(GDI+画板),
txtColor 为文本色,ARGB 格式数�?
foreColor 为当前状态前景色,ARGB 格式数�?
rc为客户区RECT结构�?rcContent为去掉内边距后的RECT结构�?
返回真取消绘制文本、前景等默认操作*/
}

```

### uiCtrlPlusObject.onDrawEnd

```aardio aardio
uiCtrlPlusObject.onDrawEnd = function(graphics,rc,bmpMem){
    /*所有绘制操作结束触发此事件,
graphics 为gdip.graphics对象(GDI+画板),
rc 为客户区RECT结构�?
bmpMem 为当前正在绘制的 gdip.bitmap 对象�?要注意此函数退出后不可继续使用 bmpMem�?可使�?bmpMem.clone,bmpMem.copy,bmpMem.getThumbnail 等复制图�?/
}

```

### uiCtrlPlusObject.onDrawForegroundEnd

```aardio aardio
uiCtrlPlusObject.onDrawForegroundEnd = function(graphics,rc,rcContent){
    /*背景前景绘制�?绘制文本前触发此事件,
graphics 为gdip.graphics对象(GDI+画板),
rc为客户区RECT结构�?rcContent为去掉内边距后的RECT结构�?/
}

```

### uiCtrlPlusObject.onDrawString

```aardio aardio
uiCtrlPlusObject.onDrawString = function(graphics,text,font,rectf,strformat,brush){
    /*自定义输出文�?请不要删除传入参数中的GDI+对象*/
    graphics.drawString(text,font,rectf,strformat,brush);
}

```

### uiCtrlPlusObject.onDropFiles

```aardio aardio
uiCtrlPlusObject.onDropFiles = function(files){
    /*接受系统拖放,files是拖放的所有文件路径名数组,嵌入编辑框必须是edit控件,richedit*/
}

```

### uiCtrlPlusObject.onFocusGot(hLostFocus)

```aardio aardio
uiCtrlPlusObject.onFocusGot = function(hLostFocus){
    ..win.setFocus(hLostFocus);/*得到焦点触发此事�?hLostFocus为失去焦点的窗口句柄,
如果在这里将hLostFocus恢复焦点,则阻止当前窗口得到焦�?/
}

```

### uiCtrlPlusObject.onFocusLost(hFocus)

```aardio aardio
uiCtrlPlusObject.onFocusLost = function(hFocus){
    /*失去焦点触发此事�?hFocus为得到焦点的窗口句柄*/
}

```

### uiCtrlPlusObject.onKeyDown

```aardio aardio
uiCtrlPlusObject.onKeyDown = function(keyCode,lParam,repeat){
    /*按下键盘�?/
}

```

### uiCtrlPlusObject.onKeyUp

```aardio aardio
uiCtrlPlusObject.onKeyUp = function(keyCode,lParam){
    /*放开键盘�?/
}

```

### uiCtrlPlusObject.onMouseActivate

```aardio aardio
uiCtrlPlusObject.onMouseActivate = function(hwndTop,hitTest,message){
    return _MA_/*鼠标点击并且将要激活窗口时触发此事�?hwndTop表示被激活的顶层窗口,
hitTest参数请参考WM_NCHITTEST消息
message为鼠标消息ID
返回值的作用请参数MSDN*/
}

```

### uiCtrlPlusObject.onMouseClick

```aardio aardio
uiCtrlPlusObject.onMouseClick = function(wParam,lParam){
    var x,y = win.getMessagePos(lParam);
    /*鼠标左键在控件上单击,
orphanWindow模式下如果阻止控件得到焦�?此事件不会被触发*/
}

```

### uiCtrlPlusObject.onMouseDoubleClick

```aardio aardio
uiCtrlPlusObject.onMouseDoubleClick = function(wParam,lParam){
    var x,y = win.getMessagePos(lParam);
    /*鼠标左键双击*/
}

```

### uiCtrlPlusObject.onMouseDown

```aardio aardio
uiCtrlPlusObject.onMouseDown = function(wParam,lParam){
    var x,y = win.getMessagePos(lParam);
    /*鼠标左键按下,
orphanWindow模式下如果阻止控件得到焦�?此事件不会被触发*/
}

```

### uiCtrlPlusObject.onMouseDrag

```aardio aardio
uiCtrlPlusObject.onMouseDrag = function(wParam,lParam){
    /*鼠标左键按下拖动,
自动捕获鼠标,允许拖出控件范围*/
}

```

```aardio aardio
uiCtrlPlusObject.onMouseDrag = function(wParam,lParam){
    var x,y = win.getMessagePos(lParam);
    /*鼠标左键按下拖动,
自动捕获鼠标,允许拖出控件范围*/
}

```

### uiCtrlPlusObject.onMouseEnter

```aardio aardio
uiCtrlPlusObject.onMouseEnter = function(wParam,lParam){
    /*鼠标移入*/
}

```

### uiCtrlPlusObject.onMouseHWheel

```aardio aardio
uiCtrlPlusObject.onMouseHWheel = function(flags,delta,lParam){
    delta = -delta/(120/3);
    /*水平滚动鼠标滚轮,flags 参数�?_MK_CONTROL 等常量表示按�?/
}

```

### uiCtrlPlusObject.onMouseHover

```aardio aardio
uiCtrlPlusObject.onMouseHover = function(wParam,lParam){
    /*鼠标悬停*/
}

```

### uiCtrlPlusObject.onMouseLeave

```aardio aardio
uiCtrlPlusObject.onMouseLeave = function(wParam,lParam){
    /*鼠标移出*/
}

```

### uiCtrlPlusObject.onMouseMove

```aardio aardio
uiCtrlPlusObject.onMouseMove = function(wParam,lParam){
    if( wParam & 0x1/*_MK_LBUTTON*/ ){
        var x,y = win.getMessagePos(lParam);
        /*鼠标移动*/
    }
}

```

### uiCtrlPlusObject.onMouseUp

```aardio aardio
uiCtrlPlusObject.onMouseUp = function(wParam,lParam){
    var x,y = win.getMessagePos(lParam);
    /*鼠标左键弹起*/
}

```

### uiCtrlPlusObject.onMouseWheel

```aardio aardio
uiCtrlPlusObject.onMouseWheel = function(flags,delta,lParam){
    delta = delta/(120/3);
    /*滚动鼠标滚轮,flags 参数�?_MK_CONTROL 等常量表示按�?/
}

```

### uiCtrlPlusObject.onPosChanged

```aardio aardio
uiCtrlPlusObject.onPosChanged = function( pos,triggeredByUser ){
    /*进度值变�?pos 参数为当前进度数�?
如果此事件由用户拖动滑块或按键盘方向键触�?�?triggeredByUser 参数�?true*/
}

```

### uiCtrlPlusObject.onRightMouseDown

```aardio aardio
uiCtrlPlusObject.onRightMouseDown = function(wParam,lParam){
    var x,y = win.getMessagePos(lParam);
    /*鼠标右键按下*/
}

```

### uiCtrlPlusObject.onRightMouseUp

```aardio aardio
uiCtrlPlusObject.onRightMouseUp = function(wParam,lParam){
    var x,y = win.getMessagePos(lParam);
    /*鼠标右键弹起*/
}

```

### uiCtrlPlusObject.onSelectChange

```aardio aardio
uiCtrlPlusObject.onSelectChange = function(prev){
    /*单选模式下已选中当前控件,prev 为同一分组之前选中的控�?同一分组之前没有选中控件�?prev �?null*/
}

```

### uiCtrlPlusObject.onStateChange

```aardio aardio
uiCtrlPlusObject.onStateChange = function(state){
    /*状态已改变*/
}

```

### uiCtrlPlusObject.onSysKeyDown

```aardio aardio
uiCtrlPlusObject.onSysKeyDown = function(keyCode,lParam,repeat){
    if(keyCode!=0x12/*_VK_ALT*/){
        /*按下键盘ALT组合�?/
    }
}

```

### uiCtrlPlusObject.onSysKeyUp

```aardio aardio
uiCtrlPlusObject.onSysKeyUp = function(keyCode,lParam){
    /*放开键盘�?/
}

```

### uiCtrlPlusObject.oncommand

```aardio aardio
uiCtrlPlusObject.oncommand = function( id,event ){
    /*控件被单�?/
}

```

### uiCtrlPlusObject.onnotify

```aardio aardio
uiCtrlPlusObject.onnotify = function(id,code,ptr){
    /*处理通知消息,
plus 控件默认不发送通知消息,
但如果绑�?tooltip 控件这些会触发这个事�?/
}

```

### uiCtrlPlusObject.orphanWindow

如果当前是子窗口,

移除窗口的WS\_CHILD样式，使窗口孤立出来悬浮于原位置,

悬浮窗口如影随形的跟随父窗口移动或改变大�?控件原来的固定边距等参数仍然有效

### uiCtrlPlusObject.orphanWindow(transparent,hwndBuddy)

创建悬浮窗口,

悬浮窗口仍然显示在原来的位置,

可选参�?@transparent 如果�?true 则转换为分层透明窗口,

可选利�?@buddy 参数将只有句柄的窗口托管在悬浮窗口之上实现相同的效果,

伙伴窗口总是会保持在悬浮窗口前面，并保持相同的大小、位�?
### uiCtrlPlusObject.paddingBottom

前景下边�?
可限制前景以及文�?文本还可以使用textPadding属性进一步增减边�?
滑块模式�?此属性将同时作用于背景色，作不会作用于背景图�?
### uiCtrlPlusObject.paddingLeft

前景左边�?
可限制前景以及文�?文本还可以使用textPadding属性进一步增减边�?
滑块模式�?此属性将同时作用于背景色，作不会作用于背景图�?
### uiCtrlPlusObject.paddingRight

前景右边�?
可限制前景以及文�?文本还可以使用textPadding属性进一步增减边�?
滑块模式�?此属性将同时作用于背景色，作不会作用于背景图�?
### uiCtrlPlusObject.paddingTop

前景上边�?
可限制前景以及文�?文本还可以使用textPadding属性进一步增减边�?
滑块模式�?此属性将同时作用于背景色，作不会作用于背景图�?
### uiCtrlPlusObject.passwordChar

指定隐藏密码的占位字�?

例如指定�?\*"隐藏密码,指定为null正常显示文本

如果调用了setCueBannerText，passwordChar不会影响提示文本

### uiCtrlPlusObject.postMessage(msg,wParam,lParam)

投递窗口消息到消息队列�?
此函数用法请参�?::User32.PostMessage

### uiCtrlPlusObject.preadjust

```aardio aardio
uiCtrlPlusObject.preadjust = function( cx,cy,wParam ) {
    /*窗口缩放后重绘前、触�?adjust 事件之前触发此事件�?所�?win.form 创建的窗体和控件都支持此事件,
�?adjust 事件不同，对 preadjust 重复赋值则覆盖而不是追加事件�?
cx 参数为窗口宽�?cy 参数为窗口高�?
wParam �?_WM_SIZE 消息参数�?/
};

```

### uiCtrlPlusObject.predraw()

刷新位图缓存并准备下次重�?
### uiCtrlPlusObject.progressPercentage

进度条当前百分比�?
如果用户正在控件上按下鼠标（例如拖动滑块），设置此属性会被忽�?
### uiCtrlPlusObject.progressPos

获取或设置进度条当前值�?
如果用户正在控件上按下鼠标（例如拖动滑块），设置此属性会被忽�?
### uiCtrlPlusObject.publish("字符串参�?,)

在窗口所在界面线程发布消�?

运行界面线程所有所有调用subscribe函数订阅此消息的函数,

可添加任意个触发参数

### uiCtrlPlusObject.radioClick()

单选模式下选中控件

### uiCtrlPlusObject.radioGroup

用于指定单选按钮分组名�?
也可以在skin函数的group属性中指定该�?
### uiCtrlPlusObject.radioValue()

单选模式下选中控件的文�?
### uiCtrlPlusObject.redraw()

刷新重绘

不重绘背�?速度较快

### uiCtrlPlusObject.redrawTransparent()

刷新重绘

如果控件添加了透明样式 \_WS\_EX\_TRANSPARENT 则重绘窗口背�?
### uiCtrlPlusObject.reduce(array,callback,debounce)

```aardio aardio
uiCtrlPlusObject.reduce(
    {/*@array 参数指定要循环处理每个元素的数组或表�?@array 指定�?false 则取消之前创建的防抖单例循环�?
@callback 指定回调函数�?回调函数中可返回本次间隔延时，以毫秒为单位�?返回 0、null、false、以及不能转换为�?0 数的值中断处理�?回调参数为下一个元素的值和索引,处理到数组尾部时回调参数�?null,
如果此时仍然返回可转换为�?0 数的�?将转到第一个数组元素重复循�?@callback 指定回调函数�?
@debounce 指定是否创建为防抖单例循环，默认�?true�?/},
    function(value,index){
        if(value){
            return 50
        }
    }
)

```

### uiCtrlPlusObject.reloadScale()

按设计时位置参数、重新调整控件位置以适应窗口当前缩放比例�?
父窗口缩放时会自动执行此操作�?
默认在启动窗口消息循环时会自适应调整所有控件�?
所以在启动消息循环前添加控件不必调用此函数�?
### uiCtrlPlusObject.repeat

背景显示模式

支持模式expand,stretch,center,tile,scale\\expand模式foreTop,foreRight,foreBottom,foreLeft为九宫格切图坐标

其他模式为显示边�?
### uiCtrlPlusObject.resize(宽度,高度)

如果指定了参数则调整窗口大小,

无论是否实际调整窗口大小,发�?\_WM\_SIZE 消息给窗�?
### uiCtrlPlusObject.right

右侧坐标

### uiCtrlPlusObject.saveScale()

根据控件当前位置、缩放比例，更新控件的设计时位置参数�?
以避免下次窗口缩放自适应调整控件当前位置更改被清除，

控件所有调整位置的属性或成员函数已自动调用此函数�?
### uiCtrlPlusObject.sendMessage(msg,wParam,lParam)

发送窗口消�?
此函数用法请参�?::User32.SendMessage

### uiCtrlPlusObject.setBackground

修改背景图像

### uiCtrlPlusObject.setBackground()

[返回对象:gdipbitmapObject](https://www.aardio.com/zh-cn/doc/library-reference/gdip/bitmap.html#gdipbitmapObject)

### uiCtrlPlusObject.setBackground(背景图像,false)

加载背景图像并禁用缓�?
该函数设置成功返回原来的背景图（gdip.bitmap 对象�?
### uiCtrlPlusObject.setBackground(背景图像,缓存�?刷新重绘)

参数@1也可以使�?xAARRGGBB格式的数值指定一个颜色�?

缓存名为可选参�?默认以路径为缓存�?设为false禁止缓存,

如果参数@1是图像数据则可以使用参数@2指定缓存�?
刷新重绘参数@3默认为true

该函数设置成功返回原来的背景图（gdip.bitmap 对象�?
### uiCtrlPlusObject.setCueBannerText

并且指定嵌入编辑框为空时的显示的默认提示文本

嵌入richedit时调用此函数会阻止拖放文件消�?

嵌入编辑框改为edit即可

### uiCtrlPlusObject.setCueBannerText("提示文本")

打开编辑模式,

并且指定文本为空时的显示的默认提示文�?
注意指定提示文本以后,

不应再直接访问editBox的text,passwordChar属�?

请改为读写plus控件的text,passwordChar属�?
### uiCtrlPlusObject.setFocus()

设置焦点

可选在参数中指定新的控件文�?
如果启用了编辑模�?此函数将光标移动文本尾部

### uiCtrlPlusObject.setFont(指定字体)

指定 LOGFONT 字体对象,或逻辑字体句柄

如果不指�?point 值并指定 h 值，字体会按控件�?DPI 缩放设置自动缩放�?
### uiCtrlPlusObject.setFont(混入字体属�?

```aardio aardio
uiCtrlPlusObject.setFont(h=-12;name="Tahoma");

```

### uiCtrlPlusObject.setFontEx(字体)

设置gdip.font字体

字体由控件接管并负责释放

### uiCtrlPlusObject.setForeRepeat("模式",是否重绘)

修改前景显示模式

支持模式expand,stretch,center,tile,scale

### uiCtrlPlusObject.setForeground

修改前景图像

### uiCtrlPlusObject.setForeground()

[返回对象:gdipbitmapObject](https://www.aardio.com/zh-cn/doc/library-reference/gdip/bitmap.html#gdipbitmapObject)

### uiCtrlPlusObject.setForeground(前景图像,缓存�?刷新重绘)

修改前景图像

参数@1也可以使�?xAARRGGBB格式的数值指定一个颜色�?

缓存名为可选参�?默认以路径为缓存�?设为false禁止缓存,

如果参数@1是图像数据则可以使用参数@2指定缓存�?
刷新重绘参数@3默认为true

该函数设置成功返回原来的前景图图（gdip.bitmap 对象�?
### uiCtrlPlusObject.setForeground(背景图像,false)

加载前景图像并禁用缓�?
该函数设置成功返回原来的背景图（gdip.bitmap 对象�?
### uiCtrlPlusObject.setForeground(颜色数�?

修改foregroundColor的�?
注意plus控件、GDI+都是ARGB格式数值表示颜色分�?�?0xAARRGGBB

与RGB的分量顺序是反过来的

### uiCtrlPlusObject.setInterval(回调函数,延时毫秒�?...)

```aardio aardio
uiCtrlPlusObject.setInterval(回调函数,延时毫秒�?...setInterval(
    function(){
        /*参数@1指定执行函数,参数@2指定执行间隔�?可选指定一个或多个回调参数，不指定回调参数则默认为:
 hwnd,message,timerId,tick,

如果在定时器中执行了win.delay等继续消息循环的代码�?在定时器退出前不会再触发同一定时器（重入）�?
定时器回调函数返回数值可修改时间间隔,
返回false取消该定时器*/
    },1000
)

```

### uiCtrlPlusObject.setParent(控件对象)

改变父窗�?
### uiCtrlPlusObject.setPieRange

设置扇形进度条范�?

### uiCtrlPlusObject.setPieRange(最小�?最大�?

切换为扇形进度条模式

在此模式下前景图或前景色被裁剪为扇形,

如果有背景色则被裁剪为圆�?背景图不裁剪,

如果指定背景图、前景图,应设为center显示模式以使圆心对齐

### uiCtrlPlusObject.setPos(x坐标,y坐标,�?�?插入位置,参数)

调整窗口位置或排�?所有参数可�?
同时指定x,y坐标则移动位�?
同时指定宽高则改变大�?
指定插入位置(句柄或\_HWND前缀常量)则调整Z�?
### uiCtrlPlusObject.setProgressRange

设置进度条范围，并切换到进度条显示模式�?
如果宽大于高显示为水平进度条，高大于宽则显示为垂直进度条�?
调用了此函数将会强制使用expand显示模式

水平进度条文本右对齐,垂直进度条文本上对齐时将限制文本输出于前景内�?
否则不改变文本输出位�?
可选用textPadding属性指定文本内边距

### uiCtrlPlusObject.setProgressRange(最小�?最大�?

设置进度条范�?
调用了此函数将会强制使用expand显示模式

### uiCtrlPlusObject.setRect(rc)

设置控件区块位置(::RECT结构�?

### uiCtrlPlusObject.setRect(rc,true)

设置控件屏幕区块位置(::RECT结构�?

### uiCtrlPlusObject.setRedraw(false)

禁止重绘

### uiCtrlPlusObject.setRedraw(true)

恢复重绘

### uiCtrlPlusObject.setRepeat("模式",是否重绘)

修改背景显示模式

支持模式expand,stretch,center,tile,scale

### uiCtrlPlusObject.setTimeout(函数或代�?延时,其他附加参数)

推迟执行指定的函数或代码

此函数异步执行参数中指定的函数，不会阻塞当前代码继续执行�?
延时参数是可选参数，以毫秒为单位，默认为0毫秒

可选用附加参数指定调用延时函数的实�?
返回值为定时器ID

### uiCtrlPlusObject.setTrackbarRange

设置滑块范围，并切换到滑块显示模式�?
如果宽大于高显示为水平滑块，高大于宽则显示为垂直滑块�?
用户拖动滑块时触�?onPosChanged 事件，可用于获取当前位置

### uiCtrlPlusObject.setTrackbarRange(最小�?最大�?

如果使用图像制作滑块控件,

请将背景、前景图像设为九宫格拉伸的expand模式,

使用前景切图在右侧或顶部预留滑块位置不拉�?

如果未指定前景图�?aardio将自动使用当前字体颜色绘制滑块按�?

同样通过前景切图预留滑块大小,边框圆角属性将作用于滑块按�?

前景色将用于绘制滑块左侧或底�?背景色将用于绘制滑块右侧或顶�?

前景边距将同时限制背景前景色的大小，但不会作用于背景图像

### uiCtrlPlusObject.show(true)

显示控件

### uiCtrlPlusObject.skin(样式�?是否禁止共享样式)

```aardio aardio
uiCtrlPlusObject.skin({
    foreground = {
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

### uiCtrlPlusObject.smoothingMode

绘图画布默认抗锯齿模�?

默认值为\_GdipSmoothingModeAntiAlias

### uiCtrlPlusObject.startAnimation

启动动画定时�?

可以在控件的onAnimation动画事件函数中修改外�?

或者在控件的onDrawContent等绘图事件函数中直接输出动画

### uiCtrlPlusObject.startAnimation(interval,beginning,change)

启动动画定时�?

interval参数指定动画时间间隔，以毫秒为单�?

@beginning 指定初始状态�?@change 指定动画完成后的状态�?

可选参�?@beginning,@change 会传�?onAnimation 回调函数作为调用参数

### uiCtrlPlusObject.startProgress()

启动进度条动�?并显示进度条,

可选用参数@1指定间隔毫秒,可选用参数@2指定每次推进的进�?
必须调用setProgressRange函数事先指定进度范围

必须指定前景色、或前景�?
### uiCtrlPlusObject.stepProgress

增加进度条的�?
### uiCtrlPlusObject.stepProgress(步进单位,是否刷新)

步进单位可以省略,默认�?

参数@2可省�?默认为true

进度条到尾部或头部则返回false,否则返回true

### uiCtrlPlusObject.stopAnimation()

停止动画定时�?
### uiCtrlPlusObject.stopProgress()

停止进度条动�?并隐藏进度条

### uiCtrlPlusObject.stringFormatFlags

```aardio aardio
uiCtrlPlusObject.stringFormatFlags = _GdipStringFormatFlagsMeasureTrailingSpaces;

```

### uiCtrlPlusObject.tabNext()

[返回对象:staticObject](static.html#staticObject)

### uiCtrlPlusObject.tabNext(移动焦点,是否反向)

获取下一个支持tab控制焦点的控�?
参数@1为true会自动移动焦点到该控�?
参数@2为true则获取上一个控�?否则获取下一个控�?
### uiCtrlPlusObject.text

控件文本

### uiCtrlPlusObject.textPadding

```aardio aardio
uiCtrlPlusObject.textPadding = {
    left = 0;
    top = 0;
    bottom = 0;
    right = 0;/*指定文本输出内边�?在前景内边距上叠�?可以使用负数,仅对文本有效*/
}

```

### uiCtrlPlusObject.textRenderingHint

```aardio aardio
uiCtrlPlusObject.textRenderingHint = _GdipTextRenderingHint;

```

### uiCtrlPlusObject.theme

外观主题,例如

winform.button.theme = "Explorer"

winform.button.theme = false

### uiCtrlPlusObject.threadCallable()

开启此控件的跨线程调用功能

### uiCtrlPlusObject.top

顶部坐标

### uiCtrlPlusObject.translateAccelerator

```aardio aardio
uiCtrlPlusObject.translateAccelerator = function(msg){
    /*返回是否快捷�?/
}

```

### uiCtrlPlusObject.translateCommand()

允许转发转发子窗口的命令（\_WM\_COMMAND）与通知（\_WM\_NOTIFY）消息，

避免子窗�?oncommand，onnotify 等回调失效�?
同时会处理子窗口�?\_WM\_CTLCOLORSTATIC 等消息，

以避免部分外观属性失�?
启用嵌入编辑框功能时已自动调用此函数

### uiCtrlPlusObject.trimming

```aardio aardio
uiCtrlPlusObject.trimming = _GdipStringTrimming;

```

### uiCtrlPlusObject.tryCreateEmbed

创建嵌入控件,返回控件容器对象,

容器对象�?\_object 成员是创建的 COM 对象,

容器对象可通过添加成员函数响应 COM 对象事件�?
容器对象的主要作用是充当访问 COM 对象的中间代理对象�?
通常使用 util.metaProperty 为容器对象添加属性元表，

属性元表可拦截属性、函数调用并调用 \_object 对象,

createEmbedEx 返回的容器已添加默认代理以直接访�?COM 对象

### uiCtrlPlusObject.tryCreateEmbed()

[返回对象:embedObject](../../../com/_.html#embedObject)

### uiCtrlPlusObject.tryCreateEmbed(clsId,embedObj)

创建嵌入控件,返回控件容器对象,

容器对象�?\_object 成员是创建的 COM 对象,

容器对象可通过添加成员函数响应 COM 对象事件�?
容器对象的主要作用是充当访问 COM 对象的中间代理对�?

@clsId 指定控件 CLSID,

可选在参数@2中指�?COM 对象绑定的容器对�?
成功返回容器对象,失败返回false,错误信息

### uiCtrlPlusObject.update()

重绘invalidate函数指定的区�?
### uiCtrlPlusObject.valid

窗口是否有效�?
窗口未关闭返�?true �?
窗口已关闭或正在关闭返回 false

### uiCtrlPlusObject.valign

文本垂直对齐,

顶对齐："top"

居中�?center"

底对齐："bottom"

图标文本对齐请使�?iconStyle 属性的 align 字段指定垂直对齐

### uiCtrlPlusObject.width

宽度

### uiCtrlPlusObject.x

前景x坐标,仅用于point绘图模式,

1�?�?之间的小数表示百分比，负数表示右侧反向坐�?
### uiCtrlPlusObject.y

前景y坐标,仅用于point绘图模式,

1�?�?之间的小数表示百分比，负数表示底部反向坐�?
## uiCtrlPlusObject.state 成员列表

### uiCtrlPlusObject.state.active

鼠标或键盘键按下状�?
注意直接修改该状态控件不负责重绘

### uiCtrlPlusObject.state.checked

是否选中状�?
注意直接修改该状态控件不负责重绘

### uiCtrlPlusObject.state.disabled

已禁�?
注意直接修改该状态控件不负责重绘

### uiCtrlPlusObject.state.dragging

是否按下鼠标且正在拖�?
### uiCtrlPlusObject.state.focus

是否已得到焦�?
注意直接修改该状态控件不负责重绘

### uiCtrlPlusObject.state.hover

鼠标是否在控件上�?
注意直接修改该状态控件不负责重绘

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/win/ui/ctrl/plus.md)

