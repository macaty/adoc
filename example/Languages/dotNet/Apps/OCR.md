[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 .NET �?OCR 图文识别

```aardio aardio
//aardio 调用 .NET �?OCR 图文识别
import win.ui;
/*DSG{{*/
var winform = win.form(text="dotNet.ocr 简单演�?;right=498;bottom=465)
winform.add(
button={cls="button";text="识别剪贴板图�?;left=257;top=399;right=441;bottom=453;db=1;dr=1;z=1};
edit={cls="edit";left=13;top=12;right=485;bottom=391;db=1;dr=1;dt=1;edge=1;hscroll=1;multiline=1;vscroll=1;z=2}
)
/*}}*/

//相关 OCR 范例�?~/example/Automation/ComputerVision/ocrLite.aardio"
import win.clip;
import dotNet.ocr;
var ocr = dotNet.ocr();

winform.button.oncommand = function(id,event){
    var hBmp = win.clip.readBitmap()
    if(!hBmp){
        winform.edit.print("剪贴板未读取到图�?)
        return;
    }

    var bmp = gdip.bitmap(hBmp);
    var ocrRet = ocr.detectBitmap(bmp);
    if(ocrRet){
        winform.edit.text = ocrRet.text;
        winform.edit.text = "";

        import web.json;
        for i,block in table.eachIndex(ocrRet.blocks){
            winform.edit.print(block.text);
            winform.edit.print(block.rect);
        }
    }
}

winform.show();

var ocrResult = ocr.detectClient(winform.hwnd);
if(ocrResult){

    //在图文识别结果里模糊搜索最接近的文本所在的区块正中点位置的坐标�?    var x,y = ocrResult.findPoint("识别剪贴板图�?,0.1);
    if(x && y){
        import mouse;
        //无句柄窗口可以直接用 winex.mouse.click() 点击
        mouse.moveToWindow(x,y,winform.hwnd);
        mouse.click();
    }

    //也可以更简单一些下面这样写
    ocrResult.click("识别剪贴板图�?,0.1);
}

win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/Apps/OCR.md)

