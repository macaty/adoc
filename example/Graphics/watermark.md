[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 在图片上添加文字水印

```aardio aardio
//文字水印
import fsys.dlg;
import gdip.bitmap;
import gdip.graphics;
import gdip.family;
import gdip.stringformat;
import win.ui;
/*DSG{{*/
var winform = win.form(text="在图片上添加文字水印";right=759;bottom=469)
winform.add(
button={cls="button";text="选择图片并添加水�?;left=277;top=400;right=482;bottom=442;z=1}
)
/*}}*/

winform.button.oncommand = function(id,event){
    // 选择图片文件
    var path = fsys.dlg.open("图片文件|*.jpg;*.png;*.bmp||", "请选择要添加水印的图片");
    if(!path) return;

    // 加载图片
    var bmp = gdip.bitmap(path);
    if(!bmp) return winform.msgboxErr("无法加载图片");

    // 创建画布
    var graphics = gdip.graphics(bmp);

    // 设置抗锯齿效�?    graphics.textRenderingHint = 3/*_TextRenderingHintAntiAliasGridFit*/;

    // 设置文字内容和颜�?    var text = "aardio 水印设置文字内容和颜�?;
    var brush = gdip.solidBrush(0x80FF0000); // 半透明白色

    // 设置文字对齐
    var strformat = gdip.stringformat();
    strformat.align = 0/*_GdipStringAlignmentNear*/;
    strformat.lineAlign = 0/*_GdipStringAlignmentNear*/;

    // 设置字体家族
    var family = gdip.family("微软雅黑");

    // 创建 10pt 大小字体，注意最后一个参数指定单�?    var font = family.createFont(10,0/*_FontStyleRegular*/,3/*_UnitPoint*/);;

    // 画布大小
    var rc = ::RECTF(0,0,bmp.width, bmp.height);

        // 计算文字在输出后的大�?    var rc = graphics.measureString(text, font,rc,strformat, brush)

        // 文字移动到右下角
    rc.x = bmp.width - rc.width;
    rc.y = bmp.height - rc.height

    // 输出文字
    graphics.drawString(text, font,rc ,strformat, brush);

    // 保存结果
    bmp.save("/水印.jpg");

    // 释放资源
    graphics.delete();
    bmp.dispose();

    winform.msgbox("水印添加成功�? );
}

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Graphics/watermark.md)

