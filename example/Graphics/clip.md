[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 剪贴板图�?
```aardio aardio
//剪贴板图�?import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio form";right=637;bottom=450;)
winform.add(
btnRead={cls="button";text="读取剪贴板图�?;left=249;top=379;right=404;bottom=419;db=1;dr=1;z=3};
btnWrite={cls="button";text="截屏并写入剪贴板";left=428;top=379;right=598;bottom=419;db=1;dr=1;z=2};
picturebox={cls="plus";left=21;top=16;right=617;bottom=360;db=1;dl=1;dr=1;dt=1;edge=1;repeat="scale";transparent=1;z=1}
)
/*}}*/

import win.clip;
import process.imageView;
import gdip.bitmap;

winform.btnRead.oncommand = function(id,event){
    var hBmp = win.clip.readBitmap()
    if(!hBmp){
        return winform.msgboxErr("剪贴板没有图�?);
    }

    //存为图像文件
    com.picture.fromBitmap(hBmp).Save("/clip.jpg")

    //转换�?GDI+ 图像
    var bmp = gdip.bitmap(hBmp);
    winform.picturebox.background = bmp;

    //存为图像文件
    bmp.save("/clip.jpg")

    //存为 16 �?BMP 文件
    var bmp16 = bmp.clone(,,,,0x21005/*_PixelFormat16bppRGB555*/);
    bmp16.save("/16.bmp");

    //预览图像
    process.imageView("/clip.jpg")
}

import gdip.snap;
winform.btnWrite.oncommand = function(id,event){

    //截屏
    var bmp = gdip.snap();

    //显示图像
    winform.picturebox.background = bmp;

    //获取位图句柄
    var hBmp = bmp.copyHandle();

    //写入剪贴�?    win.clip.writeBitmap(
        hBmp, //位图句柄
        true, //让剪贴板接管位图，也就不用再复制，也不用再释�?hBmp �?        true //清空剪贴板中其他格式数据
    );

    //如果上面的参�?@2 不是 true，就要用下面的代码释放位�?    //::DeleteObject(hBmp);
}

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Graphics/clip.md)

