[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# win.ui.simpleWindow 库模块帮助文�?
## win.ui 成员列表

### win.ui.simpleWindow

简单初始化无边框窗�?
使用plus控件创建标题栏按�?拖动边框,阴影�?

标题栏上添加最小化、最大化、关闭窗口等按钮,

并自动添加拖动边框、窗口阴影、设置窗口最大化范围�?

禁用最大化按钮以后不添加用于拖动调整窗体大小的边框

### win.ui.simpleWindow()

[返回对象:winUiSimpleWindowObject](#winUiSimpleWindowObject)

### win.ui.simpleWindow(窗体对象,字体大小,按钮宽度,按钮高度,标题栏高�?

为参数@1指定的无边框窗口添加简单的标题�?

标题栏是透明的，建议在标题栏拖一个bk控件上去设置合适的背景�?

标题栏是透明的，建议在标题栏拖一个bk控件上去设置合适的背景�?

可选使用参数@2指定标题栏按钮字体大�?以像素为单位,

可选用参数@3,@4指定关闭等按钮宽�?高度

标题栏高度为可选参�?
## winUiSimpleWindowObject 成员列表

### winUiSimpleWindowObject.\_form

标题栏所在窗�?
[返回对象:winform](_.html#winform)

### winUiSimpleWindowObject.skin(style)

```aardio aardio
winUiSimpleWindowObject.skin(
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

### winUiSimpleWindowObject.targetForm

要控制的目标窗口

[返回对象:winform](_.html#winform)

### winUiSimpleWindowObject.titlebar

标题�?static控件

[返回对象:staticObject](ctrl/static.html#staticObject)

### winUiSimpleWindowObject.titlebarClose

关闭按钮,plus控件

[返回对象:uiCtrlPlusObject](ctrl/plus.html#uiCtrlPlusObject)

### winUiSimpleWindowObject.titlebarMax

最大化按钮,plus控件

如果窗体设置了禁用最大化按钮则不创建此控�?并且不添加拖动边�?
[返回对象:uiCtrlPlusObject](ctrl/plus.html#uiCtrlPlusObject)

### winUiSimpleWindowObject.titlebarMin

最小化按钮,plus控件

如果窗体设置了禁用最小化按钮则不创建此控�?
[返回对象:uiCtrlPlusObject](ctrl/plus.html#uiCtrlPlusObject)

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/win/ui/simpleWindow.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/win/ui/simpleWindow.md')

