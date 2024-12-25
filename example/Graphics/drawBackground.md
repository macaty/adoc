[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 窗口背景贴图

```aardio aardio
//背景贴图
import win.ui;
/*DSG{{*/
var winform = win.form(text="窗口背景贴图";right=759;bottom=469)
winform.add(
bk={cls="bk";text="无窗口贴图控�?;left=563;top=70;right=736;bottom=408;bgcolor=65535;z=3};
plus={cls="plus";left=72;top=66;right=498;bottom=288;bgcolor=32768;z=1};
plus2={cls="plus";left=14;top=164;right=440;bottom=386;bgcolor=8421504;z=2}
)
/*}}*/

/*
使用此事件可以直接将背景画到缓存好的位图上以后，由aardio一次输出，
如果不是经常变动的图�?直接画到背景上可以避免添加多余的控件窗口,避免窗口间的重叠干扰导致的问题�?*/
import gdip.graphics;
var bmp = com.picture.loadBitmap("~\extensions\wizard\project2\forms\images\winform.jpg");
winform.onDrawBackground  = function(hdc,rc){
    gdi.fillRect(hdc,0x00008C,rc.copy(,150));
    gdi.fillRect(hdc,0x468C00,rc.copy(200));

    //九宫格贴�?    gdi.drawBitmap(hdc,bmp,rc.move(200,150),140,140,100,225);

    var font = ::LOGFONT(weight=400;point=9;color=0xFF);
    gdi.drawTextCenter(hdc,font,"改变窗口大小试试,任意位置贴图都可以支持九宫格",rc.move(120,150));
}

/*
用下面的函数让plus直接绘图到窗口背景上
*/
winform.plus.directDrawBackgroundOnly();

winform.plus2.background = 0x90808080;
winform.plus.background = 0x90008000;

winform.disableDragFullWindow = false;

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Graphics/drawBackground.md)

