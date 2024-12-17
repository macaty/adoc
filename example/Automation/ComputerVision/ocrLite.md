[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: string.ocrLite简单演�?
```aardio aardio
//屏幕找字完整�?import win.ui;
/*DSG{{*/
var winform = win.form(text="string.ocrLite简单演�?;right=796;bottom=504)
winform.add(
button={cls="button";text="识别剪贴板图�?;left=528;top=423;right=712;bottom=477;db=1;dr=1;z=2};
edit={cls="edit";left=497;top=36;right=764;bottom=403;db=1;dr=1;dt=1;edge=1;hscroll=1;multiline=1;vscroll=1;z=3};
plus={cls="plus";left=25;top=36;right=474;bottom=403;db=1;dl=1;dr=1;dt=1;repeat="scale";z=1}
)
/*}}*/

//相关 OCR 范例�?~/example/Languages/dotNet/Apps/OCR.aardio"
import string.ocrLite;
import string.ocrLite.defaultModels;
import win.clip;

//string.ocrLite 主要用于识别中文，识别数字改�?dotNet.ocr �?tesseract
var ocr = string.ocrLite(,true);
winform.button.oncommand = function(id,event){
    var hBmp = win.clip.readBitmap()
    if(!hBmp){
        winform.edit.print("剪贴板未读取到图�?)
        return;
    }

    var bmp = gdip.bitmap(hBmp);
    var ocrRet = ocr.detectBitmap(bmp);
    if(ocrRet){
        winform.plus.background = ocrRet.resultBitmap;

        winform.edit.text = ocrRet.text;
        winform.edit.text = "";

        import web.json;
        for i,block in table.eachIndex(ocrRet.blocks){
            winform.edit.print(block.text);
            winform.edit.print(web.json.stringify(block.points,false));
        }
    }
}

winform.show();

//请使�?string.ocrLite扩展�?以及 aardio 最新版
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

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Automation/ComputerVision/ocrLite.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Automation/ComputerVision/ocrLite.md')

