[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# gdip.bitmap 库模块帮助文�?
## gdip 成员列表

### gdip.BitmapData

```aardio aardio
class {
    int Width;
    int Height;
    int Stride;
    int PixelFormat;
    pointer Scan0;
    int Reserved;
}

```

### gdip.BitmapData()

[返回对象:gdiBitmapDataObject](#gdiBitmapDataObject)

### gdip.BitmapGetPixel

```aardio aardio
$.api("GdipBitmapGetPixel","int(POINTER Bitmap,int x,int y,int& color)")

```

### gdip.BitmapLockBits

```aardio aardio
$.api("GdipBitmapLockBits","int(POINTER Bitmap,struct rect,int flags,int PixelFormat,struct& lockedBitmapData)")

```

### gdip.BitmapSetPixel

```aardio aardio
$.api("GdipBitmapSetPixel","int(POINTER Bitmap,int x,int y,int color)")

```

### gdip.BitmapSetResolution

```aardio aardio
$.api("GdipBitmapSetResolution","int(POINTER Bitmap,float xdpi,float ydpi)")

```

### gdip.BitmapUnlockBits

```aardio aardio
$.api("GdipBitmapUnlockBits","int(POINTER Bitmap,struct  lockedBitmapData)")

```

### gdip.CloneBitmapArea

```aardio aardio
$.api("GdipCloneBitmapArea","int(float x,float y,float cx,float cy,int pixFormat,ptr bmp,ptr& bmp2)")

```

### gdip.CreateBitmapFromFile

```aardio aardio
$.api("GdipCreateBitmapFromFile","int(string FileName,pointer& Bitmap)")

```

### gdip.CreateBitmapFromGraphics

```aardio aardio
$.api("GdipCreateBitmapFromGraphics","int(int Width,int Height,pointer Graphics,pointer& Bitmap)")

```

### gdip.CreateBitmapFromHBITMAP

```aardio aardio
$.api("GdipCreateBitmapFromHBITMAP","int(POINTER hbm,int hpal,pointer& Bitmap)")

```

### gdip.CreateBitmapFromHICON

```aardio aardio
$.api("GdipCreateBitmapFromHICON","int(POINTER hicon,pointer& Bitmap)")

```

### gdip.CreateBitmapFromScan0

```aardio aardio
$.api("GdipCreateBitmapFromScan0","int(int Width,int Height,int stride,int PixelFormat,pointer scan0,pointer& Bitmap)")

```

### gdip.CreateBitmapFromStream

```aardio aardio
$.api("GdipCreateBitmapFromStream","int(POINTER stream,pointer& Bitmap)")

```

### gdip.CreateHBITMAPFromBitmap

```aardio aardio
$.api("GdipCreateHBITMAPFromBitmap","int(POINTER Bitmap,pointer& hbmReturn,int background)")

```

### gdip.bitmap()

[返回对象:gdipbitmapObject](bitmap.html#gdipbitmapObject)

### gdip.bitmap(com.picture对象)

com.pictrue对象转换为GDI+位图

### gdip.bitmap(graphics对象,100,100)

从指定的graphics对象创建GDI+位图副本

对位图的修改不会影响原来的graphics对象

参数(graphics对象,宽度,高度)

### gdip.bitmap(位图句柄)

从位图句柄创建bitmap对象

不会销毁传入的位图,须自行释�?
### gdip.bitmap(图标句柄,1/\*\_IMAGE\_ICON\*/)

从图标句柄创建bitmap对象

不会销毁传入的位图,须自行释�?
### gdip.bitmap(图片文件路径或数�?

创建GDI+位图对象

如果事先导入标准�?inet.http,这里也可以直接传入图像网址

### gdip.bitmap(�?�?

创建指定大小空位�?
### gdip.bitmap(�?�?像素格式,内存指针,行扫描宽�?

自内存指针创建指定大小位�?
像素格式使用 \_GdipPixelFormat 前缀的常量表示�?
行扫描宽度一般指素所占字节数乘以图像宽度，必须对齐为4字节的整数�?
### gdip.createBitmapFromHandle( ,\_IMAGE类型)

从句柄创建位图对�?
### gdip.loadBitmapFromString(请输入图片数�?

从内存字符串直接创建位图

### gdip.loadCachedBitmap

创建并返回图�?如果不是动画则缓存该位图

### gdip.loadCachedBitmap(图像路径或数�?缓存键名)

缓存名为可选参�?默认以路径为缓存�?
如果参数@1是图像数据则可以使用参数@2指定缓存�?

返回位图对象,

如果缓存键名明确指定为false�?
则不使用缓存直接创建并返回位�?
## gdip.bitmap 成员列表

位图对象

创建位图对象

失败返回null,以及错误信息

### gdip.bitmap.is()

参数 @1 是否 gdip.bitmap 对象

## 全局对象 成员列表

### loadCachedBitmap()

[返回对象:gdipbitmapObject](bitmap.html#gdipbitmapObject)

## gdiBitmapDataObject 成员列表

### gdiBitmapDataObject.Height

高度

### gdiBitmapDataObject.PixelFormat

像素格式�?
使用 \_GdipPixelFormat 前缀的常量表�?
### gdiBitmapDataObject.Scan0

字节数组指针

### gdiBitmapDataObject.Stride

每行字节宽度，一般指像素所占字节数乘以图像宽度�?
该宽度总是对齐�?字节的整数�?可能比像素所占的字节宽度大�?
该值如果为负数表示Scan0指向最后一�?
### gdiBitmapDataObject.Width

宽度

### gdiBitmapDataObject.bits.rows.bytes\[\]

字节数组

32位RGB,每像数字节顺序为Blue,Green,Red,Alpha

24位RGB,每像数字节顺序为Blue,Green,Red

### gdiBitmapDataObject.bits.rows.pixels\[\]

像素数组,32位整�?
使用lockData32获取32位位图数据时才有这个�?
### gdiBitmapDataObject.bits.rows\[\]

像素行数�?
## gdipbitmapObject 成员列表

### gdipbitmapObject.activeFrame

当前帧索�?
修改该属性请使用SelectActiveFrame函数

### gdipbitmapObject.clone

复制位图

### gdipbitmapObject.clone()

[返回对象:gdipbitmapObject](bitmap.html#gdipbitmapObject)

### gdipbitmapObject.clone(x,y,cx,cy,pixelFormat)

x,y指定复制区域起始坐标

cx,cy指定复制区域大小,所有参数可�?默认复制全图

像素格式默认为\_GdipPixelFormat32bppARGB

### gdipbitmapObject.copy()

复制位图

可选在参数中指定gdip.imageAttributes对象用于控制显示属�?
[返回对象:gdipbitmapObject](bitmap.html#gdipbitmapObject)

### gdipbitmapObject.copyHandle("icon")

创建并返�?HICON 图标句柄�?
调用者负责释放返回的位图句柄�?
### gdipbitmapObject.copyHandle(宽度,高度)

创建并返�?HBITMAP 位图句柄�?
可选指定宽度、高度参数�?
调用者负责释放返回的位图句柄�?
### gdipbitmapObject.createAnimation

如果图像是一个动�?创建定时器执行动�?
注意每个图像同时只能在一个窗口上创建动画

创建动画前自动删除之前创建的动画定时�?
如果图像不是动画,此函数不执行任何操作

成功返回定时器ID

### gdipbitmapObject.createAnimation(窗口对象,回调函数)

在窗口上创建定时�?

每帧动画触发回调函数,

回调函数owner参数被设为参数@1指定的窗口对�?
如果不指定控�?则默认指定为上次创建动画的控�?

如果不指定回调函�?则默认指定为控件的redrawTransparent函数

### gdipbitmapObject.dispose()

释放图像

此对象支持自动释�?不必手工调用此函�?
### gdipbitmapObject.eachFrame

如果图像支持动画，则返回一个帧迭代器�?
否则此函数返�?null�?
### gdipbitmapObject.eachFrame(loopCount)

遍历动画帧�?
每次调用帧迭代器切换到下一帧并返回当前帧所需延时，帧索引�?
动画完成迭代器返�?null �?
可选用 @loopCount 参数指定循环所有帧的次数，0 为无限循环�?
不指定参数则获取图像默认循环次数�?
示例�?
```aardio aardio
for delay,frame in bmp.eachFrame(1) {
    bmp.save("/"+frame+".gif");
}

```

### gdipbitmapObject.eachProperty

```aardio aardio
for( id,propertyItem in gdipbitmapObject.eachProperty() ){
     propertyItem.
}

```

### gdipbitmapObject.eachProperty()

[返回对象:gdipExifItemObject](#gdipExifItemObject)

### gdipbitmapObject.expandBitmap

使用九宫格绘图创建新的位图对�?

九宫格切图后边角四格固定,中间五格拉伸

### gdipbitmapObject.expandBitmap()

[返回对象:gdipbitmapObject](bitmap.html#gdipbitmapObject)

### gdipbitmapObject.expandBitmap(输出�?输出�?�?�?�?�?

所有参数为数�?不可省略

返回新的位图对象

### gdipbitmapObject.frameDimension

当前分辨率GUID

### gdipbitmapObject.getFrameDelays()

返回多帧图像每帧延时数值组成的数组,

延时单位为厘�?�?.01�?
### gdipbitmapObject.getFrameDimensionsList()

图像帧分辨率列表

该值是GUID数组

### gdipbitmapObject.getGraphics()

从图像创建画�?
[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdipbitmapObject.getLoopCount()

动画循环次数

0为一直循�?
### gdipbitmapObject.getPixel(x,y)

读取位图指定坐标(x,y)的ARGB颜色�?
### gdipbitmapObject.getPixelFormat()

返回像素格式

### gdipbitmapObject.getPropertyIds()

返回所有属性ID数组

### gdipbitmapObject.getPropertyItem()

[返回对象:gdipExifItemObject](#gdipExifItemObject)

### gdipbitmapObject.getPropertyItem(属性ID)

返回字段

### gdipbitmapObject.getResolution()

返回分辨率xdpi,ydpi

### gdipbitmapObject.getThumbnail()

[返回对象:gdipimageObject](image.html#gdipimageObject)

### gdipbitmapObject.getThumbnail(宽度,高度,是否保持比例)

获取缩略�?

返回 gdip.image 对象.

宽度,高度指定新的像素大小,也可以用小于1大于0的小数指定缩放百分比.

### gdipbitmapObject.height

高度

### gdipbitmapObject.isCached()

该对象已被缓�?
### gdipbitmapObject.isPlaying()

是否正在播放动画

### gdipbitmapObject.isValid()

图像是否有效

dispose函数释放以后返回false

### gdipbitmapObject.lockData

锁定图像内存

返回gdip.BitmapData结构�?
与lockMemory不同的是使用bits数组存储图像数据

### gdipbitmapObject.lockData()

[返回对象:gdiBitmapDataObject](#gdiBitmapDataObject)

### gdipbitmapObject.lockData(rect,\_GdipPixelFormat32bppARGB,flags)

所有参数可选，

默认使用图像的像素格式�?
@rect 参数可用 ::RECT 结构体指定区块位�?
### gdipbitmapObject.lockData32

如果返回32位像素格�?
则bits.rows\[\].pixels\[\]像素数组非空

否则返回bits.rows\[\].bytes字节数组

### gdipbitmapObject.lockData32()

[返回对象:gdiBitmapDataObject](#gdiBitmapDataObject)

### gdipbitmapObject.lockData32(rect,\_GdipPixelFormat32bppARGB,flags)

所有参数可选，

默认使用\_GdipPixelFormat32bppARGB像素格式获取数据�?
@rect 参数可用 ::RECT 结构体指定区块位�?
### gdipbitmapObject.lockMemory

锁定图像内存

返回gdip.BitmapData结构�?
### gdipbitmapObject.lockMemory()

[返回对象:gdiBitmapDataObject](#gdiBitmapDataObject)

### gdipbitmapObject.lockMemory(rect,\_GdipPixelFormat32bppARGB,flags)

所有参数可选，

默认使用图像的像素格式�?
@rect 参数可用 ::RECT 结构体指定区块位�?
### gdipbitmapObject.origHeight

原始高度�?
对于一�?gdip.bitmap 对象会一直缓存第一次读取的�?
### gdipbitmapObject.origWidth

原始宽度�?
对于一�?gdip.bitmap 对象会一直缓存第一次读取的�?
### gdipbitmapObject.removePropertyItem(属性ID)

移除字段

### gdipbitmapObject.rotateFlip(\_GdipRotate指定翻转选项)

翻转图片

### gdipbitmapObject.save("字符串参�?)

保存图像

使用参数指定的文件路径或加载图片时的路径

根据后缀名自动设定格�?

可选在参数@3使用gdip.encoder.parameter数组指定保存参数

### gdipbitmapObject.save("字符串参�?,80)

保存图像

使用参数指定的文件路径或加载图片时的路径

根据后缀名自动设定格�?
jpg文件可使用第二个参数指定图像质量,

可选在参数@3使用 gdip.encoder.parameter 数组指定保存参数

### gdipbitmapObject.saveAdd()

添加当前图像到多帧图�?
### gdipbitmapObject.saveAdd(图像)

添加其他gdip.image或gdip.bitmap对象到多帧图�?

可选使用参�?指定saveFlag，可选在参数@3使用gdip.encoder.parameter数组指定保存参数

### gdipbitmapObject.saveAdd(图像路径)

创建多帧图像,参数指定保存路径,

使用saveAdd添加帧，添加帧参数@1不能指定路径,

添加所有帧以后调用saveFlush函数即可

### gdipbitmapObject.saveToBuffer(后缀�?输出质量)

保存图像�?buffer，返�?buffer,

后缀名默认为"\*.jpg",质量默认�?00,

可选在参数@3使用gdip.encoder.parameter数组指定保存参数

### gdipbitmapObject.saveToStream

保存到内存流对象

该函数成功返回值为流对�?
### gdipbitmapObject.saveToStream()

[返回对象:fsysStreamObject](../fsys/stream.html#fsysStreamObject)

### gdipbitmapObject.saveToStream(流对�?后缀�?输出质量)

流对象请使用 fsys.stream 创建

后缀名默认为"\*.jpg",质量默认�?00,

可选在参数@4使用gdip.encoder.parameter数组指定保存参数

### gdipbitmapObject.selectActiveFrame(帧序�?

设置当前动画�?
### gdipbitmapObject.setFrameDelays()

修改多帧图像每帧延时数�?
参数必须是由数值组成的非空数组,

延时单位为厘�?�?.01�?
必须在调用saveAdd以前设置

### gdipbitmapObject.setPixel(x,y,argb)

设定位图指定坐标(x,y)的ARGB颜色�?
### gdipbitmapObject.setPropertyItem(字段结构�?

修改字段

### gdipbitmapObject.setResolution(xdpi,ydpi)

设置分辨�?
注意只能用来设置新建位图

### gdipbitmapObject.split

将图片按指定的行数列数平均拆分为小图�?
### gdipbitmapObject.split().map(命名�?

```aardio aardio
gdipbitmapObject.split().map(
    default = 1;
    hover = 2;
    active = 3;/*返回一个新�?键保持与参数相同,值自动设置为指定位置的图�?/
)

```

### gdipbitmapObject.split(列数,行数,�?�?�?�?

将图片按指定的行数列数平均拆分为小图�?
可选指定小图片的上、右、下、左边距

返回一维数�?
### gdipbitmapObject.stopAnimation()

如果此图像已运行动画，则停止动画

### gdipbitmapObject.totalFrames

动画帧总数

不是动画返回1

### gdipbitmapObject.unlockData(bmpData)

解锁图像内存

参数必须是lockData,lockData32函数锁定返回的gdip.BitmapData结构�?
### gdipbitmapObject.unlockMemory(bmpData)

解锁图像内存

参数必须是lockMemory函数锁定返回的gdip.BitmapData结构�?
### gdipbitmapObject.width

宽度

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/gdip/bitmap.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/gdip/bitmap.md')

