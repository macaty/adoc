[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# gdip.feather 库模块帮助文�?
## gdip 成员列表

### gdip.feather

用于实现图像羽化边缘效果

羽化图像边缘,返回gdip.bitmap对象

### gdip.feather()

[返回对象:gdipbitmapObject](bitmap.html#gdipbitmapObject)

### gdip.feather(bmp,radius,focusScales,blend,positions)

参数@1可指定gdip.bitmap对象,

如果参数@1是字符串,则调用gdip.bitmap创建位图,

其他所有参数都是可选参�?

radius: 指定羽化边框圆角半径,�?1时表示羽化边框为圆形

focusScales 参数使用0�?的小数指定中心焦点区域缩放百分比,类似探照灯效�?

blend,positions指定渐变颜色因子数组,渐变位置因子数组,

关于最�?个参数请参考gdip.pathGradientBrush中setBlend函数的用法说�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/gdip/feather.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/gdip/feather.md')

