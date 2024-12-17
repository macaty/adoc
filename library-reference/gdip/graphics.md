[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# gdip.graphics 库模块帮助文�?
## gdip 成员列表

### gdip.graphics()

[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdip.graphics(bitmap)

使用gdip.bitmap对象创建画板

### gdip.graphics(hdc)

使用GDI设备句柄创建画板

### gdip.graphics(image)

使用gdip.image对象创建画板

### gdip.graphics(winform)

使用窗口或控件对象创建画�?
## gdip.graphics 成员列表

### gdip.graphics.fromHwnd()

使用指定的窗口创建画�?
[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdip.graphics.fromImage()

使用gdip.image对象创建画板

[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

## gdipgraphicsObject 成员列表

### gdipgraphicsObject.\_bitmap

创建画板时使用的gdip.bitmap对象

[返回对象:gdipbitmapObject](bitmap.html#gdipbitmapObject)

### gdipgraphicsObject.\_hdc

创建画板时使用的设备上下�?
### gdipgraphicsObject.\_hwnd

创建画板时使用的句柄

### gdipgraphicsObject.\_image

创建画板时使用的gdip.image对象

[返回对象:gdipimageObject](image.html#gdipimageObject)

### gdipgraphicsObject.clear()

[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdipgraphicsObject.clear(0xFFFFFFFF)

用指定的颜色清空画板

### gdipgraphicsObject.compositingMode

```aardio aardio
gdipgraphicsObject.compositingMode = _GdipCompositingMode/*合成图像模式,SourceCopy为覆�?SourceOver为叠�?*/ ;

```

### gdipgraphicsObject.compositingQuality

```aardio aardio
gdipgraphicsObject.compositingQuality = _GdipCompositingQuality/*合成图像质量*/ ;

```

### gdipgraphicsObject.createCachedBitmap(位图对象)

创建缓存位图

### gdipgraphicsObject.delete()

释放图像

此对象支持自动释�?不必手工调用此函�?
[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdipgraphicsObject.deleteCachedBitmap(缓存位图)

删除缓存位图

### gdipgraphicsObject.drawArc()

[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdipgraphicsObject.drawArc(pen,x,y,width,height,startAngle,sweepAngle)

画圆�?
x,y指定椭圆所在矩形的左上�?width指定宽度,height指定高度,

startAngle:起始角度,以度为单位从X轴顺时针测量,水平线右侧为0�?

sweepAngle:startAngle和弧线末尾之间的扫描角度

### gdipgraphicsObject.drawBackground

画背景图

### gdipgraphicsObject.drawBackground()

[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdipgraphicsObject.drawBackground(位图对象,模式,绘图RECT,�?�?�?�?

支持模式 auto,expand,stretch,center,scale,tile,repeat-x,repeat-y

所有模式请参�?plus 控件背景模式属性说明，

auto 模式指图像超过绘图区则居中，否则缩放�?
该函数不检查参数正确�?调用者有责任保证参数正确

参数 @3 可用 ::RECT 结构体指定区块参数�?
可选使用参数@8指定 gdip.imageAttributes 对象设置显示属�?
tile,repeat-x,repeat-y 三种模式忽略显示属�?

函数返回自身

### gdipgraphicsObject.drawBezier

画贝塞尔曲线

### gdipgraphicsObject.drawBezier(pen,x1,y1,x2,y2,x3,y3,x4,y4)

画贝塞尔曲线

4个坐标点分别为：起始锚点，起始控制点，结束锚点，结束控制�?
### gdipgraphicsObject.drawBitmapRepeatX()

[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdipgraphicsObject.drawBitmapRepeatX(图像,绘图RECT,�?�?�?�?

水平平铺

参数@1 为gdip.bitmap对象�?
参数 @2 可用 ::RECT 结构体指定区块参数�?
最后的四个参数指定坐标

如果指定了右坐标则忽略左坐标,

如果指定了下坐标则忽略上坐标

### gdipgraphicsObject.drawBitmapRepeatY()

[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdipgraphicsObject.drawBitmapRepeatY(图像,绘图RECT,�?�?�?�?

垂直平铺

参数@1 为gdip.bitmap对象�?
参数 @2 可用 ::RECT 结构体指定区块参数�?
最后的四个参数指定坐标

如果指定了右坐标则忽略左坐标,

如果指定了下坐标则忽略上坐标

### gdipgraphicsObject.drawBitmapTile()

[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdipgraphicsObject.drawBitmapTile(图像,RECT区块)

绘图，重复平铺显示�?
参数 @2 可用 ::RECT 结构体指定区块参数�?
注意该函数会在执行时设置裁剪区域

执行完重置裁剪区�?
### gdipgraphicsObject.drawCachedBitmap(缓存位图,x,y)

输出缓存位图

### gdipgraphicsObject.drawCurve(画笔,任意个坐标数值参�?

画曲�?
可添加任意个成对的数值参数指定曲线经过的坐标�?
### gdipgraphicsObject.drawCurve2(画笔,曲线强度,任意个坐标参�?

画曲�?
曲线强度�?画出来的就是直线，设�?.5则相当于调用drawCurve画出来的弯曲程度,

参数@3开始可添加2个以上的::POINTF结构体参数指定曲线经过的坐标点，也可以在参数@3里用一�?::POINTF 结构体数组替�?
注意drawCurve的参数是多个数�?而drawCurve2的参数是多个 ::POINTF 结构�?

而且要注意是::POINTF，不�?:POINT

### gdipgraphicsObject.drawEllipse()

[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdipgraphicsObject.drawEllipse(pen,x,y,width,height)

画圆形、或椭圆

x,y指定椭圆所在矩形的左上�?width指定宽度,height指定高度

### gdipgraphicsObject.drawImage()

[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdipgraphicsObject.drawImage(图像,�?�?显示属�?

绘图

可使使用参数@2,参数@3指定输出坐标

可选使用参数@4指定gdip.imageAttributes对象设置显示属�?

注意此函数忽略原图DPI

### gdipgraphicsObject.drawImageCenter()

[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdipgraphicsObject.drawImageCenter(图像,RECT区块,显示属�?

绘图，保持图片大小并绝对居中显示�?
参数 @2 可用 ::RECT 结构体指定区块参数�?
可选使用参数@3指定gdip.imageAttributes对象设置显示属�?
### gdipgraphicsObject.drawImageExpand

九宫格绘�?九宫格切图后边角四格固定,中间五格拉伸

该函数不会严格检查参数、并忽略执行错误,调用该函数前必须保证参数正确

### gdipgraphicsObject.drawImageExpand()

[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdipgraphicsObject.drawImageExpand(图像,绘图RECT,�?�?�?�?显示属�?

参数@1为gdip.image或gdip.bitmap对象

参数@2使用::RECT结构体指定目标区�?

参数@3,@4,@5,@6指定九宫格切图坐�?
可选使用参数@7指定gdip.imageAttributes对象设置显示属�?
### gdipgraphicsObject.drawImagePoint()

[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdipgraphicsObject.drawImagePoint(图像,RECT区块,x,y)

绘图�?
参数 @2 可用 ::RECT 结构体指定区块参数�?
x,y指定偏移坐标

如果�?�?之间的值则为剩余空间百分比

如果为负数则为右下角坐标

### gdipgraphicsObject.drawImagePointRect()

[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdipgraphicsObject.drawImagePointRect(图像, 输出�?输出�?�?�?�?�?

将图像的指定区块输出到指定坐�?
注意该函数会受PNG,JPG的DPI设置影响输出大小

### gdipgraphicsObject.drawImageRect()

[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdipgraphicsObject.drawImageRect(图像,�?�?�?�?显示属�?

画图

参数@2,@3,@4,@5指定目标区块,

可选使用参数@6指定gdip.imageAttributes对象设置显示属�?
### gdipgraphicsObject.drawImageRectRect()

[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdipgraphicsObject.drawImageRectRect(图像,输出�?输出�?输出�?输出�?�?�?�?�?显示属�?

将图像的指定区块输出到指定区�?
参数@2,@3,@4,@5指定目标区块,

参数@6,@7,@8,@9指定图像区块,

可选使用参数@10指定gdip.imageAttributes对象设置显示属�?
### gdipgraphicsObject.drawImageScale()

[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdipgraphicsObject.drawImageScale(图像,RECT区块,显示属�?

绘图

保持比例缩放到合适大小�?
参数 @2 可用 ::RECT 结构体指定区块参数�?
可选使用参数@3指定gdip.imageAttributes对象设置显示属�?
### gdipgraphicsObject.drawImageStretch()

[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdipgraphicsObject.drawImageStretch(图像,RECT区块,显示属�?

绘图，拉伸图片到区块大小�?
参数 @2 可用 ::RECT 结构体指定区块参数�?
可选使用参数@3指定gdip.imageAttributes对象设置显示属�?
### gdipgraphicsObject.drawImageWithDpi()

[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdipgraphicsObject.drawImageWithDpi(图像,�?�?

绘图

可使使用参数@2,参数@3指定输出坐标

注意该函数会受PNG,JPG的DPI设置影响输出大小

### gdipgraphicsObject.drawLine

画线

### gdipgraphicsObject.drawLine()

[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdipgraphicsObject.drawLine(pen,x1,y1,x2,y2)

画线

参数 @pen �?gdip.pen 对象�?
参数 @x1,@y1,@x2,@y2 为坐�?
### gdipgraphicsObject.drawPath

画路�?
### gdipgraphicsObject.drawPath()

[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdipgraphicsObject.drawPath(pen,path)

画路�?
参数 @pen �?gdip.pen 对象�?
参数 @path �?gdip.path 对象

### gdipgraphicsObject.drawPie()

[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdipgraphicsObject.drawPie(pen,x,y,width,height,startAngle,sweepAngle)

画扇形、或椭圆

startAngle:起始角度,以度为单位从X轴顺时针测量,水平线右侧为0�?

sweepAngle:startAngle和弧线末尾之间的扫描角度

### gdipgraphicsObject.drawPolygon()

[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdipgraphicsObject.drawPolygon(pen,...)

绘制多边�?
pen 为画刷对�?

可使用一个数组，或多个参数指定多个绘图时经过�?::POINTF 坐标对象

### gdipgraphicsObject.drawRectangle

画方�?
### gdipgraphicsObject.drawRectangle()

[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdipgraphicsObject.drawRectangle(pen,x1,y1,width,height)

画方�?
参数 @pen �?gdip.pen 对象�?
参数 @x1,@y1 为坐标，

@width 为宽度，

@height 为高�?
### gdipgraphicsObject.drawString

输出文本

### gdipgraphicsObject.drawString()

[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdipgraphicsObject.drawString(str,font,rectf,format,brush)

输出文本

@str 参数为要输出的文�?
@font 参数�?gdip.font字体对象,

@rectf 为RECTF结构�?也可以通过RECT结构体的float函数转换而得,

@format 为gdip.stringformat对象,用于指定输出格式,

@brush�?gdip.solidBrush创建的画刷对�?
### gdipgraphicsObject.fastDrawBitmap()

[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdipgraphicsObject.fastDrawBitmap(位图对象,x,y)

快速绘�?
x,y为可选参�?默认�?

返回自身

### gdipgraphicsObject.fillEllipse()

[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdipgraphicsObject.fillEllipse(brush,x,y,width,height)

填充圆形、或椭圆

x,y指定椭圆所在矩形的左上�?width指定宽度,height指定高度

### gdipgraphicsObject.fillPath()

[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdipgraphicsObject.fillPath(brush,path)

填充路径

brush为画刷对�?path为gdip.path路径对象

### gdipgraphicsObject.fillPie()

[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdipgraphicsObject.fillPie(brush,x,y,width,height,startAngle,sweepAngle)

填充扇形、或椭圆

startAngle:起始角度,以度为单位从X轴顺时针测量,水平线右侧为0�?

sweepAngle:startAngle和弧线末尾之间的扫描角度

### gdipgraphicsObject.fillPolygon

画多边形

### gdipgraphicsObject.fillPolygon()

[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdipgraphicsObject.fillPolygon(brush,fillMode,...)

填充多边�?
brush 为画刷对�?fillMode使用\_gdipFillMode前缀的常量指�?可省�?
可使用一个数组，或多个参数指定多个绘图时经过�?::POINTF 坐标对象

### gdipgraphicsObject.fillRectangle

填充方块

### gdipgraphicsObject.fillRectangle()

[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdipgraphicsObject.fillRectangle(brush,x1,y1,width,height)

填充方块

参数 @pen �?gdip.pen 对象�?
参数 @x1,@y1 为坐标，

@width 为宽度，

@height 为高�?
### gdipgraphicsObject.getDc()

返回GDI兼容设备句柄

注意返回的句柄一定要调用releaseDc函数释放

### gdipgraphicsObject.getDpi()

返回设备DPI

默认�?6,96

### gdipgraphicsObject.interpolationMode

```aardio aardio
gdipgraphicsObject.interpolationMode = _GdipInterpolationMode/*放大缩小时使用的插值模�?/ ;

```

### gdipgraphicsObject.measureString

计算输出文本区块

### gdipgraphicsObject.measureString()

[返回对象:rectfObject](core.html#rectfObject)

### gdipgraphicsObject.measureString(str,theFont,layoutRect,stringFormat)

计算输出文本区块

@str 要计算的字符�?
@theFont 字体，gdip.font 对象

@layoutRect ::RECTF 结构�?
@stringFormat gdip.stringformat 文本格式对象

返回�?boundingBox RECTF 结构体，表示围绕输出字符串的边界

返回�?codepointsFitted 输出字符�?
返回�?linesFilled 输出行数

### gdipgraphicsObject.pageUnit

```aardio aardio
gdipgraphicsObject.pageUnit = _GdipUnit/*页面单位,例如打印时指定_UnitPixel则使用像素作为单�?/ ;

```

### gdipgraphicsObject.pixelOffsetMode

```aardio aardio
gdipgraphicsObject.pixelOffsetMode = _GdipPixelOffsetMode/*像素偏移模式*/;

```

### gdipgraphicsObject.releaseDc(hdc)

释放GDI兼容设备句柄

### gdipgraphicsObject.resetClip()

取消剪辑

[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdipgraphicsObject.resetTransform()

重置所有画布变�?
用于恢复scale,rotate,translate等画布变换效�?

[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdipgraphicsObject.restore(/\*状态索引\*)

恢复到指定状�?

状态索引值由save()函数的返回值获�?
不指定参数则撤消最近一次存储状�?
### gdipgraphicsObject.rotate

旋转画布

### gdipgraphicsObject.rotate()

[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdipgraphicsObject.rotate(旋转角度,选项)

以左上角坐标为参考点旋转画布

参数@2可省�?选项默认�?\_GdipMatrixOrderPrepend

### gdipgraphicsObject.rotateRect

旋转画布

### gdipgraphicsObject.rotateRect(rect,angle,order)

�?@rect 指定的区块中点为参考点旋转画布�?
@rect 参数可用 ::RECT 结构体指定区块位置�?
参数 @angle 为旋转角�?
参数 @3 可省�?选项默认�?\_GdipMatrixOrderPrepend

### gdipgraphicsObject.save()

存储状�?并返回状态索�? 可作为restore()函数的参�?)

### gdipgraphicsObject.scale

缩放画布

### gdipgraphicsObject.scale()

[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdipgraphicsObject.scale(宽度缩放比例,高度缩放比例,选项)

缩放画布

参数@3可省�?默认�?\_GdipMatrixOrderPrepend

### gdipgraphicsObject.scaleRect

居中缩放画布

### gdipgraphicsObject.scaleRect()

[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdipgraphicsObject.scaleRect(区块,宽度缩放比例,高度缩放比例,选项)

在参数@1中使�?:RECT结构体指定区块，并以该区块的中点为中心缩放画�?
参数@3可省�?默认�?\_GdipMatrixOrderPrepend

### gdipgraphicsObject.setClipPath()

[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdipgraphicsObject.setClipPath(路径对象,选项

设置剪切路径

选项默认�?\_GdipCombineModeReplace

### gdipgraphicsObject.setClipRect()

[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdipgraphicsObject.setClipRect(�?�?�?�?选项)

设置一块剪辑区域，用于限制绘图范围

选项使用 _GdipCombineMode_\_ 前缀的常量指�?
### gdipgraphicsObject.setClipRegion(region,combineMode)

设置一块剪辑区域，用于限制绘图范围�?
参数 @region 指定 gdip.region 区域对象�?
参数 @combineMode 可指定为 \_GdipCombineMode 前缀的常�?
### gdipgraphicsObject.smoothingMode

```aardio aardio
gdipgraphicsObject.smoothingMode = _GdipSmoothingMode/*平滑模式,可用于抗锯齿, 文本抗锯齿请使用textRenderingHint*/;

```

### gdipgraphicsObject.textRenderingHint

```aardio aardio
gdipgraphicsObject.textRenderingHint = _GdipTextRenderingHint/*文本的呈现模�?可用于抗锯齿*/;

```

### gdipgraphicsObject.transform()

[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdipgraphicsObject.transform(变换模式,图像,RECT区块,x,y)

变换画布

变换以后必须假定画布左上角坐标为0,画布大小为图像大�?

变换模式为字符串参数,支持 point,stretch,center,scale,含义�?plus 控件相同

模式�?expand"时转换为"stretch",传入其他模式忽略并返回null�?
否则执行变换并返回画布对像自�?

如果指定了point模式,必须同时指定x,y参数,用法与plus控件相同�?
可用 ::RECT 结构体指�?RECT 区块参数

### gdipgraphicsObject.translate

水平偏移画布

### gdipgraphicsObject.translate()

[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdipgraphicsObject.translate(水平偏移像素,垂直偏移像素,选项)

平移画布

参数@3可省�?默认�?\_GdipMatrixOrderPrepend

### gdipgraphicsObject.width

宽度

## graphics 成员列表

该变量名仅适用于表示gdip.graphics对象

[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/gdip/graphics.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/gdip/graphics.md')

