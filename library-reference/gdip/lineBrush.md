[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# gdip.lineBrush 库模块帮助文�?
## gdip 成员列表

### gdip.CreateLineBrush

```aardio aardio
$.api("GdipCreateLineBrush","int(struct pt,struct pt2,int c,int c2,int wrap,ptr& lineGd)")

```

### gdip.CreateLineBrushFromRect

```aardio aardio
$.api("GdipCreateLineBrushFromRect","int(struct rect,int c,int c2,int Mode,int wrap,ptr& lineGd)")

```

### gdip.CreateLineBrushFromRectWithAngle

```aardio aardio
$.api("GdipCreateLineBrushFromRectWithAngle","int(struct  rect,int c,int c2,float angle,bool scalable,int wrap,ptr& lineGd)")

```

### gdip.lineBrush

线性渐变笔�?
### gdip.lineBrush()

[返回对象:gdiplineBrushObject](#gdiplineBrushObject)

### gdip.lineBrush(渐变区块,起始颜色,结束颜色,渐变模式)

创建线性渐变笔�?
区块�?:RECTF结构�?可增加angle成员指定斜角方向,正值为顺时�?
使用数值表示颜色分�?0xAARRGGBB

注意与RGB的分量顺序是反过来的

渐变模式可省�?默认为\_GdipLinearGradientModeHorizontal

### gdip.lineBrush(起始坐标,结束坐标,起始颜色,结束颜色)

创建线性渐变笔�?
坐标�?:POINTF结构�?

使用数值表示颜色分�?0xAARRGGBB

注意与RGB的分量顺序是反过来的

## gdiplineBrushObject 成员列表

### gdiplineBrushObject.delete()

释放笔刷对象

### gdiplineBrushObject.gammaCorrection

是否启用灰度校正

### gdiplineBrushObject.getLineColors()

返回起始颜色,结束颜色

### gdiplineBrushObject.getRect()

返回::RECTF结构�?
[返回对象:rectfObject](core.html#rectfObject)

### gdiplineBrushObject.setLineColors(起始颜色,结束颜色)

使用数值表示颜色分�?0xAARRGGBB

### gdiplineBrushObject.wrapMode

_GdipWrapMode_\_/\*填充的包围模式\*/

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/gdip/lineBrush.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/gdip/lineBrush.md')

