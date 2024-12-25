[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# win.ui.simpleWindow3 库模块帮助文�?
## win.ui 成员列表

### win.ui.simpleWindow3

简单初始化无边框窗�?并创建渐变背景的标题�?

标题栏使用分层窗口实现，并使�?orphanWindow 悬浮在父窗口上面,

标题栏上添加最小化、最大化、关闭窗口等按钮,

并自动添加拖动边框、窗口阴影、设置窗口最大化范围�?

可以在窗体设计器的窗口属性中禁用最大化、最小化按钮

禁用最大化按钮以后不添加用于拖动调整窗体大小的边框

### win.ui.simpleWindow3()

[返回对象:winUiSimpleWindow3Object](#winUiSimpleWindow3Object)

### win.ui.simpleWindow3(窗体对象,字体大小,按钮宽度,按钮高度,标题栏高�?背景�?前景�?

为参数@1指定的无边框窗口添加渐变背景的标题栏,

可选使用参数@2指定标题栏按钮字体大�?以像素为单位,

可选用参数@3,@4指定关闭等按钮宽�?高度

标题栏高度为可选参�?

背景色、前景色用于指定渐变顶部、底部颜�?都是可选参�?
## winUiSimpleWindow3Object 成员列表

### winUiSimpleWindow3Object.\_form

标题栏所在窗�?
[返回对象:winform](_.html#winform)

### winUiSimpleWindow3Object.background

可用ARGB格式颜色数值指定窗口线性渐变使用的顶部颜色

### winUiSimpleWindow3Object.foreground

可用ARGB格式颜色数值指定窗口线性渐变使用的底部颜色

### winUiSimpleWindow3Object.skin(style)

```aardio aardio
winUiSimpleWindow3Object.skin(
    background = {
        hover = 0xff99ffcc;
        active = 0xffff6666;
        default = 0x00000000;
    }
    color = {
        hover = 0xff666666;
        active = 0xffffffff;
        default = 0xffffffff; /*自定义标题栏关闭、最大化、最小化按钮样式
用法与plus控件的skin函数相同*/
    }
)

```

### winUiSimpleWindow3Object.titlebar

标题�?static控件

[返回对象:staticObject](ctrl/static.html#staticObject)

### winUiSimpleWindow3Object.titlebarClose

关闭按钮,plus控件

[返回对象:uiCtrlPlusObject](ctrl/plus.html#uiCtrlPlusObject)

### winUiSimpleWindow3Object.titlebarMax

最大化按钮,plus控件

如果窗体设置了禁用最大化按钮则不创建此控�?并且不添加拖动边�?
[返回对象:uiCtrlPlusObject](ctrl/plus.html#uiCtrlPlusObject)

### winUiSimpleWindow3Object.titlebarMin

最小化按钮,plus控件

如果窗体设置了禁用最小化按钮则不创建此控�?
[返回对象:uiCtrlPlusObject](ctrl/plus.html#uiCtrlPlusObject)

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/win/ui/simpleWindow3.md)

