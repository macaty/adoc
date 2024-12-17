[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# gdip.path 库模块帮助文�?
## gdip 成员列表

### gdip.AddPathArc

```aardio aardio
$.api("GdipAddPathArc","int(PTR path,float x,float y,float width,float height,float startAngle,float sweepAngle)")

```

### gdip.AddPathBezier

```aardio aardio
$.api("GdipAddPathBezier","int(PTR path,float x1,float y1,float x2,float y2,float x3,float y3,float x4,float y4)")

```

### gdip.AddPathClosedCurve

```aardio aardio
$.api("GdipAddPathClosedCurve","int(PTR path,struct Points,int count)")

```

### gdip.AddPathCurve

```aardio aardio
$.api("GdipAddPathCurve","int(PTR path,struct Points,int count)")

```

### gdip.AddPathEllipse

```aardio aardio
$.api("GdipAddPathEllipse","int(PTR path,float x,float y,float width,float height)")

```

### gdip.AddPathLine

```aardio aardio
$.api("GdipAddPathLine","int(PTR path,float x1,float y1,float x2,float y2)")

```

### gdip.AddPathPath

```aardio aardio
$.api("GdipAddPathPath","int(PTR path,pointer addingPath,int bConnect)")

```

### gdip.AddPathPie

```aardio aardio
$.api("GdipAddPathPie","int(PTR path,float x,float y,float width,float height,float startAngle,float sweepAngle)")

```

### gdip.AddPathPolygon

```aardio aardio
$.api("GdipAddPathPolygon","int(PTR path,struct Points,int count)")

```

### gdip.AddPathRectangle

```aardio aardio
$.api("GdipAddPathRectangle","int(PTR path,float x,float y,float width,float height)")

```

### gdip.AddPathString

```aardio aardio
$.api("GdipAddPathString","int(PTR path,string str,int Length,pointer family,int style,float emSize,struct& layoutRect,ptr strFmt)")

```

### gdip.ClonePath

```aardio aardio
$.api("GdipClonePath","int(PTR path,int& clonePath)")

```

### gdip.ClosePathFigure

```aardio aardio
$.api("GdipClosePathFigure","int(PTR path)")

```

### gdip.ClosePathFigures

```aardio aardio
$.api("GdipClosePathFigures","int(PTR path)")

```

### gdip.CreatePath

```aardio aardio
$.api("GdipCreatePath","int(int brushmode,pointer& Path)")

```

### gdip.DeletePath

```aardio aardio
$.api("GdipDeletePath","int(PTR path)")

```

### gdip.ResetPath

```aardio aardio
$.api("GdipResetPath","int(PTR path)")

```

### gdip.StartPathFigure

```aardio aardio
$.api("GdipStartPathFigure","int(PTR path)")

```

### gdip.path()

[返回对象:gdippathObject](#gdippathObject)

### gdip.path(\_GdipFillMode)

创建路径对象

## gdip.path 成员列表

### gdip.path.is()

参数 @1 是否 gdip.bitmap 对象

## gdippathObject 成员列表

### gdippathObject.addArc(x,y,width,height,startAngle,sweepAngle)

添加椭圆�?
startAngle:起始角度,以度为单位从X轴顺时针测量

sweepAngle:startAngle 和弧线末尾之间的角度

### gdippathObject.addBezier(x1,y1,x2,y2,x3,y3,x4,y4)

添加贝塞尔曲�?
4个坐标点分别为：起始锚点，起始控制点，结束锚点，结束控制�?
### gdippathObject.addClosedCurve(points)

添加闭合曲线�?
参数 @points 传入一个数值数组，�?2 个数值指定一个坐标点�?x,y 坐标�?
数组可包含任意个数坐标点�?
@points 的数组成员如果是包含成对数值的数组�?
则调�?table.flat 函数自动展开�?
### gdippathObject.addClosedCurve(x1,y1,x2,y2,...)

添加闭合曲线�?
指定多个数值参数，�?2 个数值指定一个坐标点�?x,y 坐标�?
可指定任意个数坐标点

### gdippathObject.addCurve(points)

添加曲线�?
参数 @points 传入一个数值数组，�?2 个数值指定一个坐标点�?x,y 坐标�?
数组可包含任意个数坐标点�?
@points 的数组成员如果是包含成对数值的数组�?
则调�?table.flat 函数自动展开�?
### gdippathObject.addCurve(x1,y1,x2,y2,...)

添加曲线�?
指定多个数值参数，�?2 个数值指定一个坐标点�?x,y 坐标�?
可指定任意个数坐标点

### gdippathObject.addEllipse(x,y,width,height)

添加椭圆

### gdippathObject.addLine(x1,y1,x2,y2)

添加直线

### gdippathObject.addPie(x,y,width,height,startAngle,sweepAngle)

添加一个扇形轮�?
startAngle:起始角度,以度为单位从X轴顺时针测量

sweepAngle:startAngle 和弧线末尾之间的角度

### gdippathObject.addPolygon(points)

添加多边形�?
参数 @points 传入一个数值数组，�?2 个数值指定一个坐标点�?x,y 坐标�?
数组可包含任意个数坐标点�?
@points 的数组成员如果是包含成对数值的数组�?
则调�?table.flat 函数自动展开�?
### gdippathObject.addPolygon(x1,y1,x2,y2,...)

添加多边形�?
指定多个数值参数，�?2 个数值指定一个坐标点�?x,y 坐标�?
可指定任意个数坐标点

### gdippathObject.addRectangle(x,y,width,height)

添加矩形

### gdippathObject.addRoundRect(RECT,圆角大小)

添加圆角矩形

圆角大小也可以使用四个�?自左上角开始顺时针为序:

左上,右上,右下,左下

### gdippathObject.addstring(str,family,style,emSize,rclayout,strformat )

添加字符�?
### gdippathObject.closeAllFigure()

闭合所有图形开始新�?
### gdippathObject.closeFigure()

闭合当前图形开始新�?
### gdippathObject.delete()

释放路径对象

### gdippathObject.reset()

重置为空路径

### gdippathObject.startFigure()

不闭合开始新图形

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/gdip/path.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/gdip/path.md')

