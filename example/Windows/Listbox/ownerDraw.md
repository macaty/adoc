[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 列表框控件（listbox�?- GDI+自绘

```aardio aardio
//列表框控件（listbox�?- GDI+自绘
import win.ui;
/*DSG{{*/
winform = win.form(text="listbox 自绘演示(GDI+)";right=973;bottom=619)
winform.add(
listbox={cls="listbox";left=41;top=18;right=950;bottom=597;bgcolor=16777215;db=1;dl=1;dr=1;dt=1;items={};ownerDraw=1;z=1}
)
/*}}*/

winform.listbox.onMeasureItem = function(measureItem,dpiScaleX,dpiScaleY){
    //注意listbox的实际高度受行高的影�?只有自绘时才能设置行�?    measureItem.itemHeight = 61 * dpiScaleY;
}

import gdip;
winform.listbox.onDrawItem = function(drawItem,dpiScaleX,dpiScaleY){
    var rc = drawItem.rcItem;

    //创建画板
    var graphics = gdip.graphics(drawItem.hDC);

    //创建背景刷子
    var brush = gdip.solidBrush(0xFFFFFFFF);
    graphics.fillRectangle(brush,rc.left,rc.top,rc.width(),rc.height())
    brush.delete();

    //画选区渐变背景
    if( drawItem.itemState & 0x1/*_ODS_SELECTED*/){
        var p1 = ::POINTF(rc.left,rc.top)
        var p2 = ::POINTF(rc.left,rc.bottom)
        var lineBrush = gdip.lineBrush(p1/*渐变起始坐标*/, p2 /*渐变终止坐标*/ , 0x2FFFFFFF/*起始颜色*/, 0xFFFFFFE0/*结束颜色*/, 2/*_GdipWrapModeTileFlipY*/ )
        graphics.fillRectangle(lineBrush,rc.left,rc.top,rc.width(),rc.height());
        lineBrush.delete()
    }

    //第二个项目开始顶部画�?    if( drawItem.itemID > 0 ){
        var pen = gdip.pen(0xFFDCDCCC,1);
        graphics.drawLine(pen, rc.left,rc.top,rc.right,rc.top);
        pen.delete()
    }

    //获取字体
    var font = gdip.font(drawItem.hDC);
    var strformat = gdip.stringformat ();

    var str = winform.listbox.getItemText(drawItem.itemID + 1);
    var brush = gdip.solidBrush(0xFF222222);
    graphics.drawString( str , font , rc.inflate(-16,-16).float(), strformat,brush);

    //释放对象
    font.delete();
    strformat.delete();
    brush.delete();
    graphics.delete();
}

for(i=1;10;2){
    winform.listbox.add("控件属性面板中点击「行�?/ 自绘」设�?true");
    winform.listbox.add("也就是在控件创建参数里添�?ownerDraw=true");
}

winform.enableDpiScaling();
winform.show();

return win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Listbox/ownerDraw.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Listbox/ownerDraw.md')

