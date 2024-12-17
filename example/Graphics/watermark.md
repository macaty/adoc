[aardio 鏂囨。](../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鍦ㄥ浘鐗囦笂娣诲姞鏂囧瓧姘村嵃

```aardio aardio
//鏂囧瓧姘村嵃
import fsys.dlg;
import gdip.bitmap;
import gdip.graphics;
import gdip.family;
import gdip.stringformat;
import win.ui;
/*DSG{{*/
var winform = win.form(text="鍦ㄥ浘鐗囦笂娣诲姞鏂囧瓧姘村嵃";right=759;bottom=469)
winform.add(
button={cls="button";text="閫夋嫨鍥剧墖骞舵坊鍔犳按鍗?;left=277;top=400;right=482;bottom=442;z=1}
)
/*}}*/

winform.button.oncommand = function(id,event){
    // 閫夋嫨鍥剧墖鏂囦欢
    var path = fsys.dlg.open("鍥剧墖鏂囦欢|*.jpg;*.png;*.bmp||", "璇烽�夋嫨瑕佹坊鍔犳按鍗扮殑鍥剧墖");
    if(!path) return;

    // 鍔犺浇鍥剧墖
    var bmp = gdip.bitmap(path);
    if(!bmp) return winform.msgboxErr("鏃犳硶鍔犺浇鍥剧墖");

    // 鍒涘缓鐢诲竷
    var graphics = gdip.graphics(bmp);

    // 璁剧疆鎶楅敮榻挎晥鏋?    graphics.textRenderingHint = 3/*_TextRenderingHintAntiAliasGridFit*/;

    // 璁剧疆鏂囧瓧鍐呭鍜岄鑹?    var text = "aardio 姘村嵃璁剧疆鏂囧瓧鍐呭鍜岄鑹?;
    var brush = gdip.solidBrush(0x80FF0000); // 鍗婇�忔槑鐧借壊

    // 璁剧疆鏂囧瓧瀵归綈
    var strformat = gdip.stringformat();
    strformat.align = 0/*_GdipStringAlignmentNear*/;
    strformat.lineAlign = 0/*_GdipStringAlignmentNear*/;

    // 璁剧疆瀛椾綋瀹舵棌
    var family = gdip.family("寰蒋闆呴粦");

    // 鍒涘缓 10pt 澶у皬瀛椾綋锛屾敞鎰忔渶鍚庝竴涓弬鏁版寚瀹氬崟浣?    var font = family.createFont(10,0/*_FontStyleRegular*/,3/*_UnitPoint*/);;

    // 鐢诲竷澶у皬
    var rc = ::RECTF(0,0,bmp.width, bmp.height);

        // 璁＄畻鏂囧瓧鍦ㄨ緭鍑哄悗鐨勫ぇ灏?    var rc = graphics.measureString(text, font,rc,strformat, brush)

        // 鏂囧瓧绉诲姩鍒板彸涓嬭
    rc.x = bmp.width - rc.width;
    rc.y = bmp.height - rc.height

    // 杈撳嚭鏂囧瓧
    graphics.drawString(text, font,rc ,strformat, brush);

    // 淇濆瓨缁撴灉
    bmp.save("/姘村嵃.jpg");

    // 閲婃斁璧勬簮
    graphics.delete();
    bmp.dispose();

    winform.msgbox("姘村嵃娣诲姞鎴愬姛锛? );
}

winform.show();
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Graphics/watermark.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Graphics/watermark.md')

