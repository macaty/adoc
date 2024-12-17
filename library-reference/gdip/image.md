[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# gdip.image 库模块帮助文�?
## gdip 成员列表

### gdip.CloneImage

```aardio aardio
$.api("GdipCloneImage","int(PTR img,ptr& cloneImage)")

```

### gdip.GetAllPropertyItems

```aardio aardio
$.api("GdipGetAllPropertyItems","int(PTR img,int totalBufferSize,int numProperties,struct& allItems)")

```

### gdip.GetImageHeight

```aardio aardio
$.api("GdipGetImageHeight","int(PTR img,int& Height)")

```

### gdip.GetImageHorizontalResolution

```aardio aardio
$.api("GdipGetImageHorizontalResolution","int(PTR img,float& resolution)")

```

### gdip.GetImagePixelFormat

```aardio aardio
$.api("GdipGetImagePixelFormat","int(PTR img,int& PixelFormat)")

```

### gdip.GetImageThumbnail

```aardio aardio
$.api("GdipGetImageThumbnail","int(PTR img,int w,int h,pointer& thumb,pointer callback,pointer callbackData )")

```

### gdip.GetImageVerticalResolution

```aardio aardio
$.api("GdipGetImageVerticalResolution","int(PTR img,float& resolution)")

```

### gdip.GetImageWidth

```aardio aardio
$.api("GdipGetImageWidth","int(PTR img,int& Width)")

```

### gdip.GetPropertyCount

```aardio aardio
$.api("GdipGetPropertyCount","int(PTR img,int& numOfProperty)")

```

### gdip.GetPropertyIdList

```aardio aardio
$.api("GdipGetPropertyIdList","int(PTR img,int numOfProperty,struct& list)")

```

### gdip.GetPropertyItem

```aardio aardio
$.api("GdipGetPropertyItem","int(PTR img,int propId,int propSize,string& buffer)")

```

### gdip.GetPropertyItemSize

```aardio aardio
$.api("GdipGetPropertyItemSize","int(PTR img,int propId,int& size)")

```

### gdip.GetPropertySize

```aardio aardio
$.api("GdipGetPropertySize","int(PTR img,int& totalBufferSize,int& numProperties)")

```

### gdip.ImageGetFrameCount

```aardio aardio
$.api("GdipImageGetFrameCount","int(PTR img,struct dimensionID,INT& count)")

```

### gdip.ImageGetFrameDimensionsCount

```aardio aardio
$.api("GdipImageGetFrameDimensionsCount","int(PTR img,int& count)")

```

### gdip.ImageGetFrameDimensionsList

```aardio aardio
$.api("GdipImageGetFrameDimensionsList","int(PTR img,struct& dimensionIDs,int count)")

```

### gdip.ImageRotateFlip

```aardio aardio
$.api("GdipImageRotateFlip","int(PTR img,int rfType)")

```

### gdip.ImageSelectActiveFrame

```aardio aardio
$.api("GdipImageSelectActiveFrame","int(PTR img,struct& dimensionID,int frameIndex)")

```

### gdip.LoadImageFromFile

```aardio aardio
$.api("GdipLoadImageFromFile","int(ustring FileName,pointer& Image)")

```

### gdip.LoadImageFromStream

```aardio aardio
$.api("GdipLoadImageFromStream","int(POINTER stream,pointer& Image)")

```

### gdip.RemovePropertyItem

```aardio aardio
$.api("GdipRemovePropertyItem","int(PTR img,int propId)")

```

### gdip.SaveImageToFile

```aardio aardio
$.api("GdipSaveImageToFile","int(PTR img,ustring FileName,struct clsidEncoder,struct encoderParams)")

```

### gdip.SaveImageToStream

```aardio aardio
$.api("GdipSaveImageToStream","int(PTR img,PTR stream,struct clsidEncoder,struct encoderParams)")

```

### gdip.SetPropertyItem

```aardio aardio
$.api("GdipSetPropertyItem","int(PTR img,struct& Item)")

```

### gdip.image("字符串参�?)

创建GDI+L图片对象

### gdip.image()

[返回对象:gdipimageObject](image.html#gdipimageObject)

### gdip.loadImageFromString(请输入图片数�?

从内存字符串直接创建图像

## gdip.encoder 成员列表

### gdip.encoder.parameter("SaveFlag",{int v})

创建保存图像参数,用法参考函数源�?
## gdipExifItemObject 成员列表

### gdipExifItemObject.length

数据长度

### gdipExifItemObject.number

数值格�?
如果是数组仅显示第一个数�?
如果value为文本则number字段为空

### gdipExifItemObject.propId

属�?ID

### gdipExifItemObject.text

尝试转换为文本格式的值，

将对象转�?tostring 函数返回此字段�?
此字段有可能是根�?value �?\_get 元方法中动态生成�?
### gdipExifItemObject.type

数据类型

### gdipExifItemObject.value

原始数据值�?
值可能为文本、buffer、或一个结构体�?
如果是结构体,则数组值放�?array 字段�?
如果 value 为文本或 buffer �?number 字段为空

### gdipExifItemObject.value.array

数组�?
## gdipimageObject 成员列表

### gdipimageObject.activeFrame

当前帧索�?
修改该属性请使用SelectActiveFrame函数

### gdipimageObject.clone()

复制图像

[返回对象:gdipimageObject](image.html#gdipimageObject)

### gdipimageObject.createAnimation

如果图像是一个动�?创建定时器执行动�?
注意每个图像同时只能在一个窗口上创建动画

创建动画前自动删除之前创建的动画定时�?
如果图像不是动画,此函数不执行任何操作

成功返回定时器ID

### gdipimageObject.createAnimation(窗口对象,回调函数)

在窗口上创建定时�?

每帧动画触发回调函数,

回调函数owner参数被设为参数@1指定的窗口对�?
如果不指定控�?则默认指定为上次创建动画的控�?

如果不指定回调函�?则默认指定为控件的redrawTransparent函数

### gdipimageObject.dispose()

释放图像

此对象支持自动释�?不必手工调用此函�?
### gdipimageObject.eachFrame

如果图像支持动画，则返回一个帧迭代器�?
否则此函数返�?null�?
### gdipimageObject.eachFrame(loopCount)

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

### gdipimageObject.eachProperty()

```aardio aardio
for( tagId,propertyItem in gdipimageObject.eachProperty() ){
     propertyItem./*遍历图像属性字�?/
}

[返回对象:gdipExifItemObject](#gdipExifItemObject)

```

### gdipimageObject.frameDimension

当前分辨率GUID

### gdipimageObject.getFrameDelays()

返回多帧图像每帧延时数值组成的数组,

延时单位为厘�?�?.01�?
### gdipimageObject.getFrameDimensionsList()

图像帧分辨率列表

该值是GUID数组

### gdipimageObject.getGraphics()

从图像获取画�?
[返回对象:gdipgraphicsObject](#gdipgraphicsObject)

### gdipimageObject.getLoopCount()

获取动画循环次数,0为一直循�?

根据 GDI+ 的规�?循环次数�?会改�?,其他不变,

为不影响性能默认不处理这个问�?
如果要处�?步骤如下:

1、读取循环次数如果为1就进行下一�?
2、在GIF图像数据中搜索关键字"NETSCAPE2.0"

如果找到就将此图像的 $loopCount 属性赋值为2,

注意 plus 控件支持将加载好的GDI+图像作为参数

GIF动画循环次数一般不�?就是1,

其他数值基本无人使�?搞这么复杂是不必要的

### gdipimageObject.getPixelFormat()

返回像素格式

### gdipimageObject.getPropertyIds()

返回所有属性ID数组

### gdipimageObject.getPropertyItem()

[返回对象:gdipExifItemObject](#gdipExifItemObject)

### gdipimageObject.getPropertyItem(属性ID)

返回字段

### gdipimageObject.getResolution()

返回分辨率xdpi,ydpi

### gdipimageObject.getThumbnail()

[返回对象:gdipimageObject](image.html#gdipimageObject)

### gdipimageObject.getThumbnail(宽度,高度,是否保持比例)

获取缩略�?

返回 gdip.image 对象.

宽度,高度指定新的像素大小,也可以用小于1大于0的小数指定缩放百分比.

### gdipimageObject.height

高度

### gdipimageObject.isPlaying()

是否正在播放动画

### gdipimageObject.isValid()

图像是否有效

dispose函数释放以后返回false

### gdipimageObject.origHeight

原始高度�?
对于一�?gdip.image 对象会一直缓存第一次读取的�?
### gdipimageObject.origWidth

原始宽度�?
对于一�?gdip.image 对象会一直缓存第一次读取的�?
### gdipimageObject.removePropertyItem(属性ID)

移除字段

### gdipimageObject.rotateFlip(\_GdipRotate指定翻转选项)

翻转图片

### gdipimageObject.save("字符串参�?)

保存图像

使用参数指定的文件路径或加载图片时的路径

根据后缀名自动设定格�?

可选在参数@3使用gdip.encoder.parameter数组指定保存参数

### gdipimageObject.save("字符串参�?,80)

保存图像

使用参数指定的文件路径或加载图片时的路径

根据后缀名自动设定格�?
jpg文件可使用第二个参数指定图像质量,

可选在参数@3使用gdip.encoder.parameter数组指定保存参数

### gdipimageObject.saveAdd()

添加当前图像到多帧图�?
### gdipimageObject.saveAdd(图像)

添加其他gdip.image或gdip.bitmap对象到多帧图�?

可选使用参�?指定saveFlag，可选在参数@3使用gdip.encoder.parameter数组指定保存参数

### gdipimageObject.saveAdd(图像路径)

创建多帧图像,参数指定保存路径,

使用saveAdd添加帧，添加帧参数@1不能指定路径,

添加所有帧以后调用saveFlush函数即可

### gdipimageObject.saveToBuffer(后缀�?输出质量)

保存图像�?buffer，返�?buffer 对象,

后缀名默认为"\*.jpg",质量默认�?00,

可选在参数@3使用gdip.encoder.parameter数组指定保存参数

### gdipimageObject.saveToStream

保存到内存流对象,

该函数成功返回值为流对�?
### gdipimageObject.saveToStream()

[返回对象:fsysStreamObject](../fsys/stream.html#fsysStreamObject)

### gdipimageObject.saveToStream(流对�?后缀�?输出质量)

流对象请使用 fsys.stream 创建

后缀名默认为"\*.jpg",质量默认�?00,

可选在参数@4使用gdip.encoder.parameter数组指定保存参数

### gdipimageObject.selectActiveFrame(帧序�?

设置当前动画�?
### gdipimageObject.setFrameDelays()

修改多帧图像每帧延时数�?
参数必须是由数值组成的非空数组,

延时单位为厘�?�?.01�?
必须在调用saveAdd以前设置

### gdipimageObject.setPropertyItem(字段结构�?

修改字段

### gdipimageObject.stopAnimation()

如果此图像已运行动画,则停止动画并返回 true

### gdipimageObject.totalFrames

动画帧总数

不是动画返回1

### gdipimageObject.width

宽度

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/gdip/image.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/gdip/image.md')

