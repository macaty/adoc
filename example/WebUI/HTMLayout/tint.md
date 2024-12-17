[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: HTMLayout tint鍑芥暟杞崲宸ュ叿

```aardio aardio
//tint 鍑芥暟杞崲
import win.ui;
/*DSG{{*/
var winform = win.form(text="HTMLayout tint鍑芥暟杞崲宸ュ叿";right=599;bottom=399;border="dialog frame";max=false;)
winform.add(
btnTint={cls="button";text="璁＄畻";left=309;top=43;right=389;bottom=70;z=2};
edit={cls="edit";text="tint(#FF0000,-0.5, 0.9)";left=30;top=43;right=306;bottom=67;edge=1;multiline=1;z=1};
editResult={cls="edit";left=30;top=78;right=306;bottom=101;edge=1;multiline=1;z=3};
static={cls="edit";text="tint( 棰滆壊,浜害,楗卞拰搴? 浜害鎴栭ケ鍜屽害鐨勫彇鍊艰寖鍥翠负-1.0鑷?1.0 涔嬮棿琛ㄧず鐧惧垎姣旂殑灏忔暟";left=31;top=15;right=540;bottom=37;bgcolor=16777215;readonly=1;z=4}
)
/*}}*/

import web.layout;
wbLayout = web.layout( winform )

wbLayout.html = /**
<body> </body>
**/

var ltEle = wbLayout.querySelector("body");
winform.btnTint.oncommand = function(id,event){
    ltEle.style["background-color"] = winform.edit.text;
    var clr = ltEle.style["background-color"] ;
    if( clr ){
        var rgb = raw.convert({int clr = clr},{BYTE r;BYTE g;BYTE b});
        clr = string.format("#%02X%02X%02X", rgb.r,rgb.g,rgb.b )
        winform.editResult.text = clr;
    }
}

winform.show()
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/WebUI/HTMLayout/tint.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/WebUI/HTMLayout/tint.md')

