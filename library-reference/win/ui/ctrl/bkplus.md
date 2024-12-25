[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# win.ui.ctrl.bkplus 库模块帮助文�?
## win.ui.ctrl 成员列表

### win.ui.ctrl.bkplus()

无窗口控�?仅用于背景贴�?支持透明png图像,

直接输出颜色或图像到窗口背景图缓�?

因为不需要创建窗口可避免前后叠加控件后，处理不当带来的闪烁，

适合显示静态、不会频繁变动的图像

plus控件也可通过

调用directDrawBackgroundOnly函数变为背景控件

[返回对象:winuictrlbkplusObject](#winuictrlbkplusObject)

## winuictrlbkplusObject 成员列表

### winuictrlbkplusObject.argbColor

ARGB格式颜色数�?用于文本输出

### winuictrlbkplusObject.background

重新指定背景图像,支持jpg,gif,png等格�?

如果在这里指定ARGB格式颜色数值，

则删除背景图像并指定backgroundColor然后刷新�?
读取此属性时，即使未指向图像，也不会返回backgroundColor

### winuictrlbkplusObject.backgroundColor

背景颜色,ARGB格式颜色数�?
直接修改这个属性时不会刷新�?
也不会解除background属性引用的图像�?
### winuictrlbkplusObject.foreground

使用ARGB格式颜色数值指定前景色,不可指定图像,

bkplus是无窗口控件，如果要叠加前景图像，添加多个bkplus控件即可

### winuictrlbkplusObject.getPos（）

返回x,y,cx,cy,

x,y为控件坐�?cx,cy为控件宽、高

### winuictrlbkplusObject.interpolationMode

图像缩放时的默认插值模�?

默认值为\_GdipInterpolationModeHighQualityBicubic

### winuictrlbkplusObject.linearGradient

使用此属性指定线性渐变的方向角度,负数值表示使用径向渐�?

必须同时指定背景色、前景色才有�?指定图像后此属性无�?
### winuictrlbkplusObject.onDrawBackground

```aardio aardio
winuictrlbkplusObject.onDrawBackground(hdc,rc){
    /*背景绘图以后触发此回�?
hdc为当前绘图设备句�?rc为控件位�?/
}

```

### winuictrlbkplusObject.onDrawString

```aardio aardio
winuictrlbkplusObject.onDrawString = function(graphics,text,font,rectf,strformat,brush){
    /*自定义输出文�?请不要删除传入参数中的GDI+对象*/
    graphics.drawString(text,font,rectf,strformat,brush);
}

```

### winuictrlbkplusObject.paddingBottom

前景色下边距

### winuictrlbkplusObject.paddingLeft

前景色左边距

### winuictrlbkplusObject.paddingRight

前景色右边距

### winuictrlbkplusObject.paddingTop

前景色上边距

### winuictrlbkplusObject.redraw()

刷新,会导致背景窗口重建背景图缓存

不建议频繁调�?
### winuictrlbkplusObject.smoothingMode

绘图画布默认抗锯齿模�?

默认值为\_GdipSmoothingModeAntiAlias

### winuictrlbkplusObject.textRenderingHint

```aardio aardio
winuictrlbkplusObject.textRenderingHint = _GdipTextRenderingHint ;

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/win/ui/ctrl/bkplus.md)

