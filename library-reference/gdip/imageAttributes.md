[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# gdip.imageAttributes 库模块帮助文�?
## gdip 成员列表

### gdip.imageAttributes

图像显示属性控�?
### gdip.imageAttributes()

创建图像显示属性控制对�?
[返回对象:gdipImgattrObject](#gdipImgattrObject)

## gdipImgattrObject 成员列表

### gdipImgattrObject.dispose()

释放对象�?
内存回收时会自动调用此函数，

重复调用此函数将自动忽略

### gdipImgattrObject.reset(adjustType)

清除所有设�?adjustType为可选参�?
### gdipImgattrObject.setAlphaMatrix()

设置透明度调色矩�?

参数使用表示百分比的小数，例�?.5为Alpha分量调整�?0%

### gdipImgattrObject.setColor(color)

替换所有非完全透明的颜色，\\参数 @color 指定 RGBA 格式的颜色数�?
### gdipImgattrObject.setColorKey(clr1,clr2,adjustType)

参数@1指定透明�?

可选使用参数@2指定另一个透明色以确定透明色范�?

参数@3可选使用\_gdipColorAdjustType前缀的常量指定选项

### gdipImgattrObject.setColorMatrix(colorMatrix,grayMatrix,adjustType)

```aardio aardio
gdipImgattrObject.setColorMatrix({
    1;0;0;0;0;
    0;1;0;0;0;
    0;0;1;0;0;
    0;0;0;1;0;
    0;0;0;0;1/*colorMatrix为null取消调色矩阵
grayMatrix可省�?设为false时忽略灰�?也可以指定一个灰度矩�?adjustType使用_GdipColorAdjustType 前缀的常量指�?省略则默认为0*/
})

```

### gdipImgattrObject.setGamma

设置伽马�?
### gdipImgattrObject.setGamma(gamma,adjustType)

参数 @gamma 指定伽马值�?
如果不指定伽马值（null 值）则清除伽马值�?
adjustType 使用 \_GdipColorAdjustType 前缀的常量指定，省略则默认为 0�?
### gdipImgattrObject.setNegativeMatrix()

设置反相调色矩阵

### gdipImgattrObject.setRemapTable(colorMap,adjustType)

```aardio aardio
gdipImgattrObject.setRemapTable({
    0xFF00FFFF;0xFFFF0000/*ccolorMap为null取消颜色映射�?颜色映射表包含成对的颜色值数�?每一对颜色值使用后面的颜色替换前面的颜�?
adjustType使用_GdipColorAdjustType前缀的常量指�?省略则默认为0*/
})

```

### gdipImgattrObject.setRgba(r,g,b,a)

设置r,g,b,a分量的变化比�?

参数使用表示百分比的小数，例�?.5表示对应分量调整�?0%,

所有参数可选，默认值都�?

### gdipImgattrObject.setThreshold

设置阈�?
### gdipImgattrObject.setThreshold(threshold,adjustType)

参数 @threshold 指定阈值�?
如果不指定阈值（null 值）则清除阈值�?
阈值是一个介�?0 �?1 之间的值，该值指定每个颜色分量的截止点�?
adjustType 使用 \_GdipColorAdjustType 前缀的常量指定，省略则默认为 0�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/gdip/imageAttributes.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/gdip/imageAttributes.md')

