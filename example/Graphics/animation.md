[aardio 鏂囨。](../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鑷畾涔夊姩鐢绘紨绀?
```aardio aardio
//鑷粯鍔ㄧ敾
import win.ui;
/*DSG{{*/
var winform = win.form(text="鑷畾涔夊姩鐢绘紨绀?;right=577;bottom=419)
winform.add(
plus={cls="plus";left=446;top=143;right=646;bottom=343;z=1}
)
/*}}*/

//缁樺浘鍑芥暟
winform.plus.onDrawContent = function(graphics,rc){

    //鏃嬭浆鐢绘澘
    graphics.rotateRect(rc,winform.plus.animationState);

    //鍒涘缓鐢诲埛
    var brush = gdip.solidBrush(0xFF84FF26);
    var brush2 = gdip.solidBrush(0xFF0080FF);

    //鐢诲乏鍙冲崐鍦?    var w,h = rc.width(),rc.height();
    graphics.fillPie(brush, 0, 0, w, h, 90, 180);
    graphics.fillPie(brush2, 0, 0, w, h, 90, -180);

    //鐢婚奔澶?    graphics.fillPie(brush, w/4-1, h/2, w/2, h/2, 90, -180);
    graphics.fillPie(brush2, w/4+1, 0, w/2, h/2, 90, 180);

    //鐢婚奔鐪?    graphics.fillEllipse(brush, w/2-10, h/4-10, 20, 20);
    graphics.fillEllipse(brush2, w/2-10, h/4*3-10, 20, 20);

    brush.delete();
    brush2.delete();
}

//鍔ㄧ敾鐘舵�佹帶鍒跺嚱鏁?winform.plus.onAnimation = function(state){
    return state + 3;
}

//寮�濮嬪姩鐢?winform.plus.startAnimation(12,0);

//鎮诞鎺т欢绐楀彛
winform.plus.orphanWindow(true);

winform.show()
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Graphics/animation.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Graphics/animation.md')

