[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用打印�?
```aardio aardio
//打印
import win.ui;
/*DSG{{*/
var winform = win.form(text="调用打印�?;right=759;bottom=469;border="dialog frame";max=false)
winform.add(
btnEnumPrinters={cls="button";text="列出所有打印机";left=446;top=217;right=697;bottom=285;z=4};
btnPrint={cls="button";text="调用API打印";left=446;top=46;right=697;bottom=114;z=1};
btnPrintDefault={cls="button";text="默认打印机输�?;left=446;top=132;right=697;bottom=200;z=5};
btnWbPrint={cls="button";text="使用HTML打印";left=446;top=302;right=697;bottom=370;z=2};
edit={cls="edit";left=40;top=36;right=417;bottom=429;edge=1;multiline=1;z=3}
)
/*}}*/

import win.dlg.print;
import sys.printer;

//调用打印对话�?GDI+打印
winform.btnPrint.oncommand = function(id,event){

    import win.dlg.print;
    var printDlg = win.dlg.print(winform);
    if(!printDlg.doModal()) return;

    var pdc = sys.printer.device(printDlg.hdc);
    pdc.start(
        function(hdcPrinter){
            //GDI+绘图
            import gdip.graphics;
            import gdip.family;
            import gdip.solidBrush;

            var graphics = gdip.graphics(hdcPrinter);
            graphics.pageUnit = 2/*_UnitPixel,打印单位改为使用像素*/

            var brush = gdip.solidBrush(0xFFFF0000);
            var family = gdip.family("宋体");
            var strformat = gdip.stringformat();
            var curFont = family.createFont(  15,2/*_GdipFontStyleItalic*/, 2/*_GdipUnitPixel*/)
            graphics.drawString( "Hellow world! 打印测试!!"  , curFont
            ,  gdip.RECTF(15,15,500,150), strformat,brush);
            brush.delete()
            curFont.delete()
            strformat.delete();
            family.delete();
        }
    );

    //结束打印
    printDlg.free()
}

//直接选定默认打印机输�?winform.btnPrintDefault.oncommand = function(id,event){

    var printer = sys.printer();
    var pdc = printer.createDevice(
        dmPaperSize = 9/*_DMPAPER_A4*/; //小票打印机可以设�?,普通打印机使用 _DMPAPER_ 前缀常量指定纸张大小，例�?_DMPAPER_A4 指定为A4�?        dmOrientation = 0;//横向打印�?,纵向打印�?
        //dmPaperWidth = 800;//纸张宽度
        //dmPaperLength = 580;//纸张长度
    );

    pdc.start(
        function(hdcPrinter){
            ::Gdi32.TextOut(hdcPrinter,20,20,"测试打印",4);
        }
    );

    pdc.close();
}

//列出所有打印机
winform.btnEnumPrinters.oncommand = function(id,event){

    for printerName,serverName,attributes in sys.printer.each(){
        winform.edit.print(printerName,serverName,attributes)
    }
}

//HTML格式打印
winform.btnWbPrint.oncommand = function(id,event){
    import web.mshtml;
    wbPrint = web.mshtml();
    wbPrint.write("测试一�?)
    wbPrint.getDoc().execCommand("print")
}

winform.show()
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/System/Printer/print.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/System/Printer/print.md')

