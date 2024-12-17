[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# win.ui.shadow 库模块帮助文�?
关于无边框窗�?
无边框窗口：指的是在窗体设计器中将窗体的边框(border) 属性设�?"none"�?这种窗口不再有边框、标题栏�?
注意隐藏标题栏、并将边框设�?"resizable"等不是无边框窗口�?这种效果在不同操作系统上显示效果都很差，要么是多出一圈，要么顶上多出一块�?不要这么做�?
无边框窗口只要使用下面的代码就可以在窗口周围添加阴影�?并同时使用阴影实现完美的可拖动改变大小效果（�?resizable 边框 ）�?
import win.ui.shadow;
win.ui.shadow(winform);

尤其是嵌入浏览器组件，直接使�?win.ui.resizeBorder 添加可拖动边框可能不起作用�?win.ui.shadow 可以通过阴影实现 win.ui.resizeBorder 的功能�?
如果只想添加阴影，不想支持可拖动边框，可以下面这样写�?
import win.ui.shadow;
win.ui.shadow(winform).setResizeBorder(false)

在无边框窗口上，可以自行实现标题栏按钮，调用以下函数模拟标题栏按钮消�?
winform.hitMax() //模拟点击最大化按钮
winform.hitMin() //模拟点击最小化按钮
winform.hitClose() //模拟点击关闭按钮

winform.onMouseDown = function(wParam,lParam){
winform.hitCaption()

}

标准库提供了以下的类可以直接在无边框窗口上创建虚拟的标题栏以及可拖动边框:

win.ui.simpleWindow 实现最普通的标题栏�?win.ui.simpleWindow2 实现的标题栏没有最大化按钮�?win.ui.simpleWindow3 标题栏使用分层窗口实现，并使�?orphanWindow 悬浮在父窗口上面�?
## win.ui 成员列表

### win.ui.shadow

阴影边框

创建阴影边框

创建阴影�?窗体对象的\_shadowWindow属性被设置为此对象

### win.ui.shadow()

[返回对象:winUiShadowObject](#winUiShadowObject)

### win.ui.shadow(窗体对象,透明�?阴影大小,外圆�?内圆�?阻影颜色,暗部插值位�?聚焦系数)

除参数@1以外,其他所有参数可�?
透明度默认为70,255为不透明

阴影大小默认�?像素

外圆角默认为阴影大小

内圆角默认为�?
阴影颜色默认�?xFF000000,FF为透明�?
暗部插值位置默认为0.15,这个值是阴影内侧暗部插值点距外边界的百分比

聚焦系数默认�?5,以该系数乘以阴影大小换算为距离外边界的百分比,

加大聚焦系数会淡化阴�?
## winUiShadowObject 成员列表

### winUiShadowObject.\_form

[返回对象:winform](_.html#winform)

### winUiShadowObject.onDrawShadow(hdc,hMemDc,hMemBitmap,width,height)

```aardio aardio
winUiShadowObject.onDrawShadow = function(hdc,hMemDc,hMemBitmap,width,height){
    var graphics = ..gdip.graphics(hMemDc);
    graphics.smoothingMode = 4/*_GdipSmoothingModeAntiAlias*/;

    graphics.delete();
}

```

### winUiShadowObject.setResizeBorder(true)

允许通过拖动阴影边框改变父窗口大�?
如果窗口当前已经应用win.ui.resizeBorder添加了拖动边�?

则默认启用此属�?不再需要调用此函数

### winUiShadowObject.show(true)

暂时显示或隐藏阴�?
阴影会跟随所有者窗体自动显示隐�?此函数仅用于特殊情况

### winUiShadowObject.transparent()

设置透明�?参数�?�?之间的小�?
通过wiform.transprent修改窗口透明度时,

会自动调用wiform.\_shadowWindow.transprent函数同步透明�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/win/ui/shadow.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/win/ui/shadow.md')

