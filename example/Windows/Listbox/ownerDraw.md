[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鍒楄〃妗嗘帶浠讹紙listbox锛?- GDI+鑷粯

```aardio aardio
//鍒楄〃妗嗘帶浠讹紙listbox锛?- GDI+鑷粯
import win.ui;
/*DSG{{*/
winform = win.form(text="listbox 鑷粯婕旂ず(GDI+)";right=973;bottom=619)
winform.add(
listbox={cls="listbox";left=41;top=18;right=950;bottom=597;bgcolor=16777215;db=1;dl=1;dr=1;dt=1;items={};ownerDraw=1;z=1}
)
/*}}*/

winform.listbox.onMeasureItem = function(measureItem,dpiScaleX,dpiScaleY){
    //娉ㄦ剰listbox鐨勫疄闄呴珮搴﹀彈琛岄珮鐨勫奖鍝?鍙湁鑷粯鏃舵墠鑳借缃楂?    measureItem.itemHeight = 61 * dpiScaleY;
}

import gdip;
winform.listbox.onDrawItem = function(drawItem,dpiScaleX,dpiScaleY){
    var rc = drawItem.rcItem;

    //鍒涘缓鐢绘澘
    var graphics = gdip.graphics(drawItem.hDC);

    //鍒涘缓鑳屾櫙鍒峰瓙
    var brush = gdip.solidBrush(0xFFFFFFFF);
    graphics.fillRectangle(brush,rc.left,rc.top,rc.width(),rc.height())
    brush.delete();

    //鐢婚�夊尯娓愬彉鑳屾櫙
    if( drawItem.itemState & 0x1/*_ODS_SELECTED*/){
        var p1 = ::POINTF(rc.left,rc.top)
        var p2 = ::POINTF(rc.left,rc.bottom)
        var lineBrush = gdip.lineBrush(p1/*娓愬彉璧峰鍧愭爣*/, p2 /*娓愬彉缁堟鍧愭爣*/ , 0x2FFFFFFF/*璧峰棰滆壊*/, 0xFFFFFFE0/*缁撴潫棰滆壊*/, 2/*_GdipWrapModeTileFlipY*/ )
        graphics.fillRectangle(lineBrush,rc.left,rc.top,rc.width(),rc.height());
        lineBrush.delete()
    }

    //绗簩涓」鐩紑濮嬮《閮ㄧ敾绾?    if( drawItem.itemID > 0 ){
        var pen = gdip.pen(0xFFDCDCCC,1);
        graphics.drawLine(pen, rc.left,rc.top,rc.right,rc.top);
        pen.delete()
    }

    //鑾峰彇瀛椾綋
    var font = gdip.font(drawItem.hDC);
    var strformat = gdip.stringformat ();

    var str = winform.listbox.getItemText(drawItem.itemID + 1);
    var brush = gdip.solidBrush(0xFF222222);
    graphics.drawString( str , font , rc.inflate(-16,-16).float(), strformat,brush);

    //閲婃斁瀵硅薄
    font.delete();
    strformat.delete();
    brush.delete();
    graphics.delete();
}

for(i=1;10;2){
    winform.listbox.add("鎺т欢灞炴�ч潰鏉夸腑鐐瑰嚮銆岃涓?/ 鑷粯銆嶈涓?true");
    winform.listbox.add("涔熷氨鏄湪鎺т欢鍒涘缓鍙傛暟閲屾坊鍔?ownerDraw=true");
}

winform.enableDpiScaling();
winform.show();

return win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Listbox/ownerDraw.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Listbox/ownerDraw.md')

