[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 自定义动画演�?
```aardio aardio
//自绘动画
import win.ui;
/*DSG{{*/
var winform = win.form(text="自定义动画演�?;right=577;bottom=419)
winform.add(
plus={cls="plus";left=446;top=143;right=646;bottom=343;z=1}
)
/*}}*/

//绘图函数
winform.plus.onDrawContent = function(graphics,rc){

    //旋转画板
    graphics.rotateRect(rc,winform.plus.animationState);

    //创建画刷
    var brush = gdip.solidBrush(0xFF84FF26);
    var brush2 = gdip.solidBrush(0xFF0080FF);

    //画左右半�?    var w,h = rc.width(),rc.height();
    graphics.fillPie(brush, 0, 0, w, h, 90, 180);
    graphics.fillPie(brush2, 0, 0, w, h, 90, -180);

    //画鱼�?    graphics.fillPie(brush, w/4-1, h/2, w/2, h/2, 90, -180);
    graphics.fillPie(brush2, w/4+1, 0, w/2, h/2, 90, 180);

    //画鱼�?    graphics.fillEllipse(brush, w/2-10, h/4-10, 20, 20);
    graphics.fillEllipse(brush2, w/2-10, h/4*3-10, 20, 20);

    brush.delete();
    brush2.delete();
}

//动画状态控制函�?winform.plus.onAnimation = function(state){
    return state + 3;
}

//开始动�?winform.plus.startAnimation(12,0);

//悬浮控件窗口
winform.plus.orphanWindow(true);

winform.show()
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Graphics/animation.md)

