[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# aardio 范例: GDI+ 绘图演示 —�?gdip 库操�?
```aardio aardio
//GDI+ 绘图基础
import win.ui;
import win.ui.menu;
import com.picture;
/*DSG{{*/
var winform = win.form(text="GDI+ 绘图演示 —�?gdip 库操�?;right=566;bottom=424;)
winform.add(
btnBmp={cls="button";text="位图修改";left=207;top=383;right=355;bottom=416;db=1;dr=1;z=5};
btnDrawString={cls="button";text="GDI+ 输出文字";left=207;top=344;right=355;bottom=377;db=1;dr=1;z=2};
btnExpand={cls="button";text="九宫格绘�?;left=369;top=383;right=517;bottom=416;db=1;dr=1;z=6};
btnGraphics={cls="button";text="GDI+ 绘图基础";left=47;top=344;right=195;bottom=377;db=1;dr=1;z=1};
btnImage={cls="button";text="GDI+ 图片";left=48;top=383;right=196;bottom=416;db=1;dr=1;z=4};
btnPathText={cls="button";text="GDI+ 路径文字";left=368;top=344;right=516;bottom=377;db=1;dr=1;z=3}
)
/*}}*/

//导入 GDI+ �?实际开发建议仅导入 gdip 名字空间下需要用到的�?import gdip;

winform.btnGraphics.oncommand = function(id,event){

    //创建画板
    var graphics = gdip.graphics(  winform )

    //创建画笔,画笔pen只能画一个轮�?画线)
    var pen = gdip.pen( 0xFFFF0000, 1, 2/*_GdipUnitPixel*/ );

    //画一条线 - 需要指定画�?Pen)
    graphics.drawLine( pen, 10, 10, 200, 100).drawRectangle( pen, 30, 30, 100, 100)

    //画曲�?参数可以是任意个数坐标数�?坐标数值必须成对指定x,y坐标)
    graphics.drawCurve(pen,
        10,10,
        100,100,
        50,150,
        200,200,
        50,250
    )

    //画矩�? - 描边需要画�?Pen)
    //graphics.drawRectangle( pen, 30, 30, 100, 100);

    /*
    画笔(pen)负责描边画线,
    而刷�?brush)就负责填充、喷涂颜�?在PS里面有个油漆桶、或者说是喷枪就类似这里的刷�?brush)�?    GDI+提供了SolidBrush(实色�?、HatchBrush(阴影�?、TextureBrush(纹理�?、LinearGradientBrush(渐变�?和PathGradientBrush(路径�?等五种画�?    创建一个蓝�?透明度为0xAA的刷�?
    */
    var brush = gdip.solidBrush(0xAA0000FF);

    //用刷子填充矩形内�?    graphics.fillRectangle( brush, 30, 30, 100, 100 )

    //创建渐变刷子
    var p1 = ::POINTF(10,10)
    var p2 = ::POINTF(100,100)
    var lineBrush = gdip.lineBrush(p1/*渐变起始坐标*/, p2 /*渐变终止坐标*/ , 0xFF0000FF/*起始颜色*/, 0xFFFF0000/*结束颜色*/, 2/*_GdipWrapModeTileFlipY*/ )

    //为了圆形画的平滑自然,加上抗锯齿功�?    graphics.smoothingMode = 4/*_GdipSmoothingModeAntiAlias*/ ;

    //画圆形、或椭圆
    graphics.fillEllipse(  brush, 150/*x坐标*/, 50/*y坐标*/,150/*�?/, 120/*�?/);

    //用渐变色刷子填充矩形内部
    graphics.fillRectangle( lineBrush, 100, 100, 100, 100)

    //释放资源
    pen.delete()
    brush.delete()
    lineBrush.delete()
}

winform.btnExpand.oncommand = function(id,event){

    var bmp = gdip.bitmap("/expand.jpg");

    //内存中先绘图
    var x,y,cx,cy = winform.getPos()
    var bmpExpand = bmp.expandBitmap(cx,cy-120,30,30,30,30);
    bmpExpand.graphics.drawImageExpand(bmp,::RECT(0,0,cx,cy-120),30,30,30,30);
    bmp.dispose();

    //在屏幕上显示
    var graphics = gdip.graphics(  winform )
    graphics.drawImage(bmpExpand,0,0);

    //释放资源
    bmpExpand.dispose();
    graphics.delete();
}

winform.btnBmp.oncommand = function(id,event){

    //从文件创建位�?    var bmp = gdip.bitmap("\.gdip.jpg")

    //获取大小
    var width = bmp.width;
    var height = bmp.height;

    //获取位图数据
    var bmpdata = bmp.lockData32();

    //修改图像内存数据
    for(h=1;bmp.height ){
        for(w=1;bmp.width){
            bmpdata.bits.rows[h].pixels[w] = 0xFFFF0000;
        }
    }

    //解除内存锁定、刷新的位图数据
    bmp.unlockData(bmpdata);

    //图形对象graphics(可以看作是画�?
    var graphics = gdip.graphics(  winform )
    graphics.drawImageRect(  bmp, 20,20, 100, 200)  //指定输出大小100*200
}

winform.btnImage.oncommand = function(id,event){

    //从文件载入图�?    img = gdip.image ( "\.gdip.jpg" )
    width = img.width;
    height = img.height;
    img.dispose();//释放图片

    //从字符串直接载入图片  gdip.LoadBitmapFromString 的用法与下面的相�?    img = gdip.image($"\.gdip.jpg" )

    //图形对象graphics(可以看作是画�?
    var graphics = gdip.graphics(  winform )
    //var graphics = gdip.graphics( img )//也可以使用这个函数直接在图片上创建画�?    //graphics.clear(0xFFFFFFFF); //用指定的颜色清空画板

    //旋转画布
    graphics.rotate( 10, 1/*_GdipMatrixOrderAppend*/ )
    //将画布向�?向下平移10px,50px
    graphics.translate(  10, 50, 1/*_GdipMatrixOrderAppend*/ )

    //设置一块剪辑区�?限制绘图区块)
    graphics.setClipRect(  10, 20, 100, 100, 0/*_GdipCombineModeReplace*/ );
    graphics.resetClip() //取消剪辑

    graphics.drawImage( img, 0, 0) //普通画图片,不需要指定大�?画的图似有变�?不推荐使�?    graphics.drawImageRect( img, 20,20, 100, 200)  //指定输出大小100*200
    graphics.drawImageRectRect( img, 0, 0, 50, 50,/*前面为输出区�?后面是从原图截取的区�?/  0,  0, 300, 300 )

    //创建画刷
    var textureBrush = gdip.textureBrush(img, 1/*_GdipWrapModeTileFlipX*/ );
    graphics.fillRectangle( textureBrush, 200, 200, 500, 500);
    textureBrush.delete();

    //防止图片盖住按钮
    winform.btnPathText.redraw();
    winform.btnImage.redraw();
    winform.btnDrawString.redraw()
    winform.btnGraphics.redraw();
}

winform.btnPathText.oncommand = function(id,event){

    //图形对象graphics(可以看作是画�?
    var graphics = gdip.graphics(winform)

    //加上抗锯齿功�?    graphics.smoothingMode = 4/*_GdipSmoothingModeAntiAlias*/ ;

    //创建画笔,画笔pen只能画一个轮�?画线描边)
    var pen = gdip.pen( 0xFF222222, 2,2/*_GdipUnitPixel*/ );

    //创建刷子,画刷可以对一个东西进行填�?刷子)�?    var brush = gdip.solidBrush(0xFFDEDEDE);

    //创建FontFamily
    family = gdip.family( "Verdana"  );

    //创建stringFormat
    strformat = gdip.stringformat ( );
    //设置样式
    strformat.align = 0/*_GdipStringAlignmentNear*/;

    //设置文字区域
    rclayout = ..gdip.RECTF(50,20,500,150);

    //创建一个文字路�?    path = gdip.path();

    path.addArc(0, 0, 30, 20, -90, 180);
    path.startFigure();
    path.addCurve(
        5,30,
        20,40,
        50,30
    )
    path.addstring( "aardio", family, 1/*_GdipFontStyleBold*/, 24, rclayout, strformat);
    path.addPie(260, 10, 40, 40, 40, 110);

    //fillPath填充路径
    graphics.fillPath( brush, path)

    //drawPath描边
    graphics.drawPath( pen, path)

    //删除所有GDI+对象
    brush.delete();
    pen.delete() ;
    strformat.delete();
    family.delete();
    path.delete();
}

winform.btnDrawString.oncommand = function(id,event){

    //图形对象graphics(可以看作是画�?
    var graphics = gdip.graphics(  winform )

    //创建刷子
    var brush = gdip.solidBrush(0xFFFF0000);

    //创建FontFamily
    var family = gdip.family("宋体");

    //创建stringFormat
    var strformat = gdip.stringformat ( );

    //设置样式
    strformat.align = 0/*_GdipStringAlignmentNear*/;

    //创建Font
    var curFont = family.createFont(  15,2/*_GdipFontStyleItalic*/, 2/*_GdipUnitPixel*/)

    //设置文字抗据�?    graphics.smoothingMode = 4/*_GdipSmoothingModeAntiAlias*/ ;

    //消除走样,且边作平滑处�?    graphics.textRenderingHint = 3/*_GdipTextRenderingHintAntiAliasGridFit*/;

    //设置文字区域
    rclayout = gdip.RECTF();
    rclayout.x = 15
    rclayout.y = 15
    rclayout.width = 500 //在这里指的是宽度
    rclayout.height = 150 //在这里指的是高度

    graphics.drawString( "Hellow world! 这是我们第一个GDI+文字~!!"  , curFont
    , rclayout, strformat,brush);

    //删除所有GDI+对象
    brush.delete()
    curFont.delete()
    strformat.delete();
    family.delete();
}

winform.show(true);
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Graphics/gdip.md)

