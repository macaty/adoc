[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 截屏选区

```aardio aardio
//截屏选区
import gdip.snap;
import mouse.screenArea;
var screenArea = mouse.screenArea();
screenArea.onSelectionChanged = function(rc){

    var bmp = gdip.snap.file("/test.jpg",screenArea.hwnd,rc);
    owner.close();

    raw.explore("/test.jpg");
}
screenArea.doModal();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Graphics/screenArea.md)

