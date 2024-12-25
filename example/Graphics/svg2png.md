[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# aardio 范例: SVG �?PNG

```aardio aardio
//SVG �?PNG
import web.form.snap;

//SVG �?PNG( Win10 及以上系�?)，参�?@4,@5 指定图像大小
web.form.snap("https://dev.w3.org/SVG/tools/svgweb/samples/svg-files/whatwg.svg","/svg.png",,32,32 );

//浏览图像
import process.imageView;
process.imageView("/svg.png");

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Graphics/svg2png.md)

