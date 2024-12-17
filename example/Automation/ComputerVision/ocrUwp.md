[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 屏幕找字简�?
```aardio aardio
//屏幕找字简�?
if( _WIN10_LATER ){
    //注意现在低于 Win10 的系统已经很罕见，并且越来越少�?
    //下面调用 Win10 自带 OCR 组件
    //这实际上是一�?UWP 组件，但没关�?aardio 可以轻松打破此限制�?    import mouse;
    import dotNet.ocr;
    var ocr = dotNet.ocr();

    var ocrResult = ocr.detectScreen()
    var x,y = ocrResult.findPoint("把鼠标移动到这里",0.1);
    mouse.moveTo(x,y,true)

    /*
    如果要后台找图、模拟鼠标点击，
    可以改用 ocr.detectWindow(hwnd) 在指定的窗口找字,
    找到按钮以后，可以用 winex.mouse.click(hwnd,x,y) 函数后台点击�?    这种方法适用很多无句柄窗口（无法通过传统的窗口句柄控制）�?    */
}
else {
    //调用免费开源的 chineseocr_lite，不要求必须 Win10 系统
    import mouse;
    import string.ocrLite;
    import string.ocrLite.defaultModels;

    //string.ocrLite 主要用于识别中文，识别数字建议改�?dotNet.ocr �?tesseract
    var ocr = string.ocrLite();
    var ocrResult = ocr.detectScreen();
    var x,y = ocrResult.findPoint("把鼠标移动到这里",0.1);
    mouse.moveTo(x,y,true);
}

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Automation/ComputerVision/ocrUwp.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Automation/ComputerVision/ocrUwp.md')

