[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调整伽马�?
```aardio aardio
//调整伽马�?import gdip.bitmap;
import gdip.graphics;
import gdip.imageAttributes;

//打开图像文件，返回位图对象，路径开始为单个波浪线表�?EXE 所在目录（开发时�?aardio.exe 所在目录）
var bmp = gdip.bitmap("~/example/Graphics/.gdip.jpg")

//创建图像属性操作对象�?var iAttr = gdip.imageAttributes()

//调整伽马�?iAttr.setGamma(2.2);

//使用新的伽马值属性复制图像，此函数内部需要绘图，必须提前导入 gdip.graphics
var bmpNew = bmp.copy(iAttr);

//保存图像
bmpNew.save("/gamma.jpg");

//查看图像
import process.imageView;
process.imageView("/gamma.jpg");

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Graphics/gamma.md)

