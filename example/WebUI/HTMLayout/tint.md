[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: HTMLayout tint函数转换工具

```aardio aardio
//tint 函数转换
import win.ui;
/*DSG{{*/
var winform = win.form(text="HTMLayout tint函数转换工具";right=599;bottom=399;border="dialog frame";max=false;)
winform.add(
btnTint={cls="button";text="计算";left=309;top=43;right=389;bottom=70;z=2};
edit={cls="edit";text="tint(#FF0000,-0.5, 0.9)";left=30;top=43;right=306;bottom=67;edge=1;multiline=1;z=1};
editResult={cls="edit";left=30;top=78;right=306;bottom=101;edge=1;multiline=1;z=3};
static={cls="edit";text="tint( 颜色,亮度,饱和�? 亮度或饱和度的取值范围为-1.0�?1.0 之间表示百分比的小数";left=31;top=15;right=540;bottom=37;bgcolor=16777215;readonly=1;z=4}
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

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/WebUI/HTMLayout/tint.md)

