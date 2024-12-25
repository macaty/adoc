[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 网络图像/裁剪

```aardio aardio
//网络图像/裁剪
import gdip.bitmap;
import inet.http;//导入此库可支持网络图�?
//多线程加载网络图像，在窗口程序中也不会卡界面
var bitmap = gdip.bitmap( "https://先把这里改为有效地址好吗" )
var bitmapNew = bitmap.clone(65,20,120,50)

/*
var bitmapNew = gdip.bitmap(50,50);
bitmapNew.graphics.drawImageRectRect(bitmap,0,0,50,50,30,30,50,50)
*/

//bitmapNew.save("/testHttp.jpg")

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Graphics/http.md)

