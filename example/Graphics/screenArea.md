[aardio 鏂囨。](../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鎴睆閫夊尯

```aardio aardio
//鎴睆閫夊尯
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

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Graphics/screenArea.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Graphics/screenArea.md')

