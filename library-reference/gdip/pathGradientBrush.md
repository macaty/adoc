[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# gdip.pathGradientBrush 库模块帮助文�?
## gdip 成员列表

### gdip.pathGradientBrush

路径渐变笔刷

### gdip.pathGradientBrush()

[返回对象:gdippathGradientbrushObject](#gdippathGradientbrushObject)

### gdip.pathGradientBrush(路径对象)

参数是gdip.path对象

## gdippathGradientbrushObject 成员列表

### gdippathGradientbrushObject.delete()

释放路径对象

### gdippathGradientbrushObject.gammaCorrection

是否允许伽马校正

### gdippathGradientbrushObject.setBlend(颜色因子数组,位置因子数组)

参数@1使用小数表示的百分比代表色彩渐变的度,

0表示起点�?1表示完全转变为终点色

合成位置�?表示起点,1表示终点,第一个合成位置必须是0,最后一个必须是1

### gdippathGradientbrushObject.setCenterColor(颜色)

指定中心颜色

颜色请使�?xAARRGGBB格式数�?
### gdippathGradientbrushObject.setCenterPoint(x,y)

设置中心点坐�?
### gdippathGradientbrushObject.setFocusScales(x聚焦缩放,y聚焦缩放)

对中心焦点进行缩�?参数为x轴、y轴的缩放比例,

使中心颜色不仅显示在中心�?而是显示于围绕中心点进行缩放的路径内�?
被缩放的中心焦点路径内部使用中心颜色填充

### gdippathGradientbrushObject.setInterpolationColors(插值颜色数�?插值位置数�?

定义多色渐变

数组元素都是数�?长度必须相等

插值位置以小数表示百分�?开始必须为0表示外边�?最后一个必须为1

### gdippathGradientbrushObject.setSurroundColors(颜色数组)

指定环绕颜色

参数可以是数�?也可以是多个颜色数值参�?

颜色请使�?xAARRGGBB格式数�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/gdip/pathGradientBrush.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/gdip/pathGradientBrush.md')

