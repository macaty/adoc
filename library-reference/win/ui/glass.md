[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# win.ui.glass 库模块帮助文�?
## win.ui 成员列表

### win.ui.glass

玻璃窗口

### win.ui.glass()

[返回对象:winUiGlassObject](#winUiGlassObject)

### win.ui.glass(窗口对象,背景�?圆角大小,阴影�?阴影大小)

窗体如果指定WS\_MAXIMIZEBOX样式则添加拖动调整大小边�?
除参数@1必须指定winfom对象以外,其他所有参数可�?

参数默认值及具体用法请查看支持库源码

## winUiGlassObject 成员列表

### winUiGlassObject.\_form

[返回对象:winform](_.html#winform)

### winUiGlassObject.onDrawShadow(hdc,hMemDc,hMemBitmap,width,height)

```aardio aardio
winUiGlassObject.onDrawShadow = function(hdc,hMemDc,hMemBitmap,width,height){
    var graphics = ..gdip.graphics(hMemDc);
    graphics.smoothingMode = 4/*_GdipSmoothingModeAntiAlias*/;

    graphics.delete();
}

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/win/ui/glass.md)

