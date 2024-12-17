[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# win.ui.ctrl.splitter 库模块帮助文�?
用法说明

要点�?
1. 使用控件�?split 函数拆分多个控件�?
   例如:


   ```
   winform.splitter1.split( winform.edit1,winform.edit2 )

   ```


   参数也可以是控件数组，每个控件数组必须包含位于拆分条同一侧的控件�?
   例如:


   ```
   winform.splitter1.split( winform.edit1,{ winform.edit2,winform.edit3} )

   ```

2. 在调整窗口大小时，拆分条会负责让被拆分的控件吸附在自己的两侧�?
   但是被拆分控件以及拆分条本身的其他固定边距属性、自适应大小属性应当自行根据需要设置�?

## win.ui.ctrl 成员列表

### win.ui.ctrl.splitter

拆分条控件支持库

### win.ui.ctrl.splitter()

拆分条控�?
[返回对象:splitterObject](#splitterObject)

## splitterObject 成员列表

### splitterObject.\_parentForm

创建该控件的父窗口（win.form对象�?

设计时窗体容器是所有拖放在窗体上的控件�?\_parentForm,

即使窗口移除子窗口样式、更改父子关系，或以 orphanWindow显示,

控件�?\_parentForm 始终都不会改�?
[返回对象:winform](../_.html#winform)

### splitterObject.adjust

```aardio aardio
splitterObject.adjust = function( cx,cy,wParam ) {

};

```

### splitterObject.adjust()

调整窗口 \- 自定义事件函�?
### splitterObject.bottom

底部坐标

### splitterObject.capture

是否捕获全局鼠标消息

### splitterObject.className

运行时类�?
### splitterObject.close()

关闭控件窗口

### splitterObject.cls

设计时类�?
### splitterObject.disabled

是否禁用

### splitterObject.getClientRect()

控件客户区块位置(::RECT结构�?

[返回对象:rectObject](../../../global/_.html#rectObject)

### splitterObject.getParent()

返回父窗�?
[返回对象:splitterObject](#splitterObject)

### splitterObject.getPos()

返回相对坐标,�?�?
x,y,cx,cy=win.getPos(hwnd)

### splitterObject.getRect()

控件区块位置(::RECT结构�?

### splitterObject.getRect(true)

控件屏幕区块位置(::RECT结构�?

### splitterObject.height

高度

### splitterObject.hide

控件是否隐藏

### splitterObject.horz

是否水平拆分�?
### splitterObject.hwnd

控件句柄

### splitterObject.id

控件ID

### splitterObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/)

使窗口绘图区无效

### splitterObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/,0)

使窗口绘图区无效

不刷新背�?
### splitterObject.left

左侧坐标

### splitterObject.ltControl

拆分条左边或上边的控件�?
可以是控件对象，也可以是包含控件的数组�?
只能调用 split 函数修改此属性�?
[返回对象:staticObject](static.html#staticObject)

### splitterObject.ltMin

前面的控件最小尺�?
### splitterObject.modifyStyle(remove,add,swpFlags)

修改窗口样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### splitterObject.modifyStyleEx(remove,add,swpFlags)

修改窗口扩展样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS\_EX_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS\_EX_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### splitterObject.onSplitterMoved

```aardio aardio
splitterObject.onSplitterMoved = function(l,t,r,b){
    /*拆分条已被拖拽移动到新位置，l,r,r,b 分别为左上右下坐�?/
}

```

### splitterObject.postMessage(msg,wParam,lParam)

投递窗口消息到消息队列�?
此函数用法请参�?::User32.PostMessage

### splitterObject.rbControl

拆分条右边或下边的控件�?
可以是控件对象，也可以是包含控件的数组�?
只能调用 split 函数修改此属性�?
[返回对象:staticObject](static.html#staticObject)

### splitterObject.rbMin

后面的控件最小尺�?
### splitterObject.redraw()

刷新

### splitterObject.redrawTransparent()

刷新

透明背景时请使用此函数替代redraw()

### splitterObject.right

右侧坐标

### splitterObject.sendMessage(msg,wParam,lParam)

发送窗口消�?
此函数用法请参�?::User32.SendMessage

### splitterObject.setParent(控件对象)

改变父窗�?
### splitterObject.setPos(x坐标,y坐标,�?�?插入位置,参数)

调整窗口位置或排�?所有参数可�?
同时指定x,y坐标则移动位�?
同时指定宽高则改变大�?
指定插入位置(句柄或\_HWND前缀常量)则调整Z�?
### splitterObject.setRect(rc)

设置控件区块位置(::RECT结构�?

### splitterObject.setRect(rc,true)

设置控件屏幕区块位置(::RECT结构�?

### splitterObject.show(true)

显示控件

### splitterObject.split(前面的控�?后面的控�?

指定需要拆分的控件�?
参数可以是控件对象，也可以是包含控件对象的数组�?
同一数组中的控件必须位于拆分条的同一侧�?
被折分的控件可在控件属性中指定是否支持自动调整大小�?
也可以将更多控件可放入子窗口并以 custom 控件作为容器加载，然后再拆分�?
listbox 反复改变高度会因为自动适应项目行高而越来越�?

要用拆分条改�?listbox 高度时最好也放入 custom 容器

### splitterObject.text

控件文本

### splitterObject.theme

外观主题,例如

winform.button.theme = "Explorer"

winform.button.theme = false

### splitterObject.top

顶部坐标

### splitterObject.translateAccelerator

```aardio aardio
splitterObject.translateAccelerator = function(msg){
    /*返回是否快捷�?/
}

```

### splitterObject.update()

重绘invalidate函数指定的区�?
### splitterObject.width

宽度

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/win/ui/ctrl/splitter.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/win/ui/ctrl/splitter.md')

