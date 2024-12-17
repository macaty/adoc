[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鍒楄〃妗嗘帶浠讹紙listbox锛?- GDI 鑷粯

```aardio aardio
//鍒楄〃妗嗘帶浠讹紙listbox锛?- GDI 鑷粯
import win.ui;
/*DSG{{*/
var winform = win.form(text="listbox鑷粯(GDI鏂瑰紡)";right=757;bottom=467)
winform.add(
listbox={cls="listbox";left=12;top=11;right=745;bottom=457;bgcolor=16777215;db=1;dl=1;dr=1;dt=1;items={};ownerDraw=1;vscroll=1;z=1}
)
/*}}*/

winform.listbox.onMeasureItem = function(measureItem,dpiScaleX,dpiScaleY){
    measureItem.itemHeight = 61 * dpiScaleY;
}

winform.listbox.onDrawItem = function(drawItem,dpiScaleX,dpiScaleY){
     gdi.selectBrush(

        function(hdc,pen,brush){

            var rc = drawItem.rcItem;
            gdi.fillRect(hdc,0xFFFFFF,rc);

            if (drawItem.itemID > 0) {
                gdi.drawLine(hdc,rc.left, rc.top,rc.right, rc.top);
            }

            if (drawItem.itemState & 1/*_ODS_SELECTED*/) {
                gdi.fillGradient(hdc,rc,0xFFFFFF, 0xFFC4B5,1/*_GRADIENT_FILL_RECT_V*/)
            }

            var str = winform.listbox.getItemText(drawItem.itemID + 1);

            var font = ::LOGFONT(weight=400;point=10;color=0x000000);
            gdi.textOut(hdc,font,str,rc.left + 18/dpiScaleX, rc.top + 26/dpiScaleY);

        },drawItem.hDC,0xF5FDFF/*鑳屾櫙鑹?/,0xEEEEEE/*鐢荤瑪鑹?/)
}

for(i=1;10;2){
    winform.listbox.add("鎺т欢灞炴�ч潰鏉夸腑鐐瑰嚮銆岃涓?/ 鑷粯銆嶈涓?true");
    winform.listbox.add("涔熷氨鏄湪鎺т欢鍒涘缓鍙傛暟閲屾坊鍔?ownerDraw=true");
}

winform.show();
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Listbox/gdi.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Listbox/gdi.md')

