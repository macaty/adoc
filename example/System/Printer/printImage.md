[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鎵撳嵃鍥惧儚

```aardio aardio
//鎵撳嵃鍥惧儚
import sys.printer;
var printImage = function(filepath){

    var printer = sys.printer();
    var pdc = printer.createDevice(
        dmPaperSize = 9/*_DMPAPER_A4*/; //A4 绾?        dmOrientation = 0;//妯悜鎵撳嵃涓?,绾靛悜鎵撳嵃涓?
    );

    pdc.start(
        function(hdcPrinter,rc){

            //GDI+缁樺浘
            import gdip.graphics;
            import gdip.bitmap;

            var graphics = gdip.graphics(hdcPrinter);
            graphics.pageUnit = 2/*_UnitPixel,鎵撳嵃鍗曚綅鏀逛负浣跨敤鍍忕礌*/;

            var bmp = gdip.bitmap(filepath);

            //淇濇寔姣斾緥缂╂斁鎵撳嵃鍐呭浠ョ鍚堜粙璐?            graphics.drawImageScale(bmp,rc);
        }
    );
}

/*
import fsys;
fsys.enum( "\img-test", "*.png",
    function(dir,filename,fullpath,findData){
        if(filename){
           printImage(fullpath);
        }
    },false
);
*/

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/System/Printer/printImage.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/System/Printer/printImage.md')

