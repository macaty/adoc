[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 裁剪图像

```aardio aardio
//裁剪图像
import gdip.path;
import gdip.bitmap;
import gdip.graphics;

//加载图像
var srcImage = gdip.bitmap("C:\Users\jacen\Desktop\abc.png");

//创建输出图像
var destImage = gdip.bitmap(srcImage.width, srcImage.height);

//创建画板
var graphics = destImage.getGraphics();

//创建路径
var path = gdip.path();

//指定要裁剪的 4 个点，支持不规则形状�?path.addPolygon({
    {20,20},
    {100,100},
    {100,300},
    {20,300}
});

//设置裁剪路径
graphics.setClipPath(path);

//绘图
graphics.drawImage(srcImage, 0, 0);

//保存输出图像
destImage.save("/裁剪后的图像.png");

//释放对象
path.delete();
graphics.delete();
srcImage.dispose();
destImage.dispose();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Graphics/setClipPath.md)

