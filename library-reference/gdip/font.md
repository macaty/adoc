[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# gdip.font 库模块帮助文�?
## gdip 成员列表

### gdip.CloneFont

```aardio aardio
$.api("GdipCloneFont","int(POINTER curFont,pointer& cloneFont)")

```

### gdip.CreateFontFromDC

```aardio aardio
$.api("GdipCreateFontFromDC","int(POINTER hDc,pointer& createdfont)")

```

### gdip.CreateFontFromLogfont

```aardio aardio
$.api("GdipCreateFontFromLogfont","int(POINTER hDc,struct logfont,pointer& createdfont)")

```

### gdip.GetFamily

```aardio aardio
$.api("GdipGetFamily","int(POINTER curFont,pointer& family)")

```

### gdip.GetFontHeight

```aardio aardio
$.api("GdipGetFontHeight","int(POINTER curFont,pointer Graphics,float& Height)")

```

### gdip.GetFontSize

```aardio aardio
$.api("GdipGetFontSize","int(POINTER curFont,float& size)")

```

### gdip.GetFontStyle

```aardio aardio
$.api("GdipGetFontStyle","int(POINTER curFont,int& style)")

```

### gdip.GetFontUnit

```aardio aardio
$.api("GdipGetFontUnit","int(POINTER curFont,int& unit)")

```

### gdip.GetLogFont

```aardio aardio
$.api("GdipGetLogFont","int(POINTER curFont,pointer Graphics,struct& logfont)")

```

### gdip.font

指定字形风格（例如常规、粗体）的字体（font）对�?
创建字体

### gdip.font()

[返回对象:gdipfontObject](font.html#gdipfontObject)

### gdip.font(fontFamily,emSize,style,unit)

创建字体,

参数@fontFamily 指定 gdip.family 对象�?
参数@emSize指定大小,

可选参数@style 使用 \_GdipFontStyle 前缀的常量指定字形样式，默认�?\_GdipFontStyleRegular�?
可选参数@unit 指定单位,默认值为\_GdipUnitPixel

### gdip.font(hdc)

hdc为空则取屏幕DC

### gdip.font(hdc,LOGFONT字体)

使用LOGFONT字体创建GDI+字体对象

可自动支持fonts名字空间下已导入的自带字�?
参数hdc为空则取屏幕DC

## gdipfontObject 成员列表

### gdipfontObject.clone()

复制字体

[返回对象:gdipfontObject](font.html#gdipfontObject)

### gdipfontObject.delete()

删除字体

### gdipfontObject.getHeight(graphics)

显示高度

数�?
### gdipfontObject.getLogFont(graphics)

返回LOGFONT字体对象

### gdipfontObject.getSize()

字体大小

数�?
### gdipfontObject.getStyle()

样式

数�?
### gdipfontObject.getUnit()

单位

数�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/gdip/font.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/gdip/font.md')

