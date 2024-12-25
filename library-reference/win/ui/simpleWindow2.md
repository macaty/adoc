[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# win.ui.simpleWindow2 库模块帮助文�?
## win.ui 成员列表

### win.ui.simpleWindow2

简单初始化无边框窗�?
标题栏上添加最小化、关闭窗口等按钮,

并自动添加窗口阴�?不创建最大化按钮,不添加拖动边�?
### win.ui.simpleWindow2()

[返回对象:winUiSimpleWindow2Object](#winUiSimpleWindow2Object)

### win.ui.simpleWindow2(窗体对象,字体大小,按钮宽度,按钮高度,右边�?上边�?

参为参数@1指定的无边框窗口添加简单的标题�?

标题栏是透明的，建议在标题栏拖一个bk控件上去设置合适的背景�?

标题栏是透明的，建议在标题栏拖一个bk控件上去设置合适的背景�?

可选使用参数@2指定标题栏按钮字体大�?以像素为单位,

可选用参数@3,@4指定关闭等按钮宽�?高度

## winUiSimpleWindow2Object 成员列表

### winUiSimpleWindow2Object.\_form

标题栏所在窗�?
[返回对象:winform](_.html#winform)

### winUiSimpleWindow2Object.skin(style)

```aardio aardio
winUiSimpleWindow2Object.skin(
    background = {
        hover = 0xff99ffcc;
        active = 0xffff6666;
        default = 0x00000000;
    }
    color = {
        hover = 0xff666666;
        active = 0xffffffff;
        default = 0xffffffff; /*自定义标题栏关闭、最小化按钮样式
用法与plus控件的skin函数相同*/
    }
)

```

### winUiSimpleWindow2Object.targetForm

要控制的目标窗口

[返回对象:winform](_.html#winform)

### winUiSimpleWindow2Object.titlebar

标题�?static控件

[返回对象:staticObject](ctrl/static.html#staticObject)

### winUiSimpleWindow2Object.titlebarClose

关闭按钮,plus控件,

[返回对象:uiCtrlPlusObject](ctrl/plus.html#uiCtrlPlusObject)

### winUiSimpleWindow2Object.titlebarMin

最小化按钮,plus控件,

如果窗体设置了禁用最小化按钮则不创建此控�?
[返回对象:uiCtrlPlusObject](ctrl/plus.html#uiCtrlPlusObject)

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/win/ui/simpleWindow2.md)

