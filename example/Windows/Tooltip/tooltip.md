[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 控件提示 - 鼠标悬停在超链接上试�?
```aardio aardio
//提示控件
import fonts.fontAwesome;
import win.ui;
/*DSG{{*/
var winform = win.form(text="控件提示 - 鼠标悬停在超链接上试�?;right=492;bottom=254;bgcolor=4448391;max=false)
winform.add(
plus={cls="plus";text="http://www.aardio.com";left=80;top=79;right=404;bottom=107;color=15793151;font=LOGFONT(h=-24);notify=1;z=1};
plusTracking={cls="plus";text="手动控制的汽泡提�?;left=187;top=201;right=442;bottom=238;bgcolor=-5197169;font=LOGFONT(h=-16;name='FontAwesome';charset=0);notify=1;z=2}
)
/*}}*/

import win.ui.tooltip;

//在所有者窗�?winform 上创�?tooltip 提示控件
var tooltipCtrl = win.ui.tooltip( winform );

//添加一个自动模式的控件提示（TOOLINFO 对象，简�?tool �?var toolInfoPlus = tooltipCtrl.addTool(winform.plus,"这是一个超链接" )

/*
自动模式的提示会在鼠标放到关系控件上时自动显示，离开时自动隐藏�?当然也可以使用下面的方法修改提示文本�?*/
import process;
winform.plus.oncommand = function( id,event ){
    process.openUrl(owner.text);//打开网页

    //这个函数可以重复调用没有关系(会自动删除原来的控件)
    var toolInfoPlus = tooltipCtrl.addTool(winform.plus,"已经点过的超链接")

    //这样写也可以改控件提�?    toolInfoPlus.setText("已经点过的超链接")

    //这样写也可以改控件提�?    tooltipCtrl.setText("已经点过的超链接2",winform.plus);
}

/*
下面创建一个手动跟踪模式的提示控件
*/
var balloonTipCtrl = win.ui.tooltip.tracking(winform,false);
winform.plusTracking.onMouseEnter = function(wParam,lParam){
    var x,y,cx,cy = winform.plusTracking.getPos(true);

    //手动显示提示
    balloonTipCtrl.setText("手动跟踪模式的提示控�?).trackPopup(true,x+20,y+cy );
}

winform.plusTracking.onMouseLeave = function(wParam,lParam){
    balloonTipCtrl.trackPopup(false); //手动关闭提示
}

winform.plusTracking.skin({
    background = {
        default=0xFF8FB2B0;
        hover=0xFF928BB3
    }
})

winform.plus.skin(
    color = {
        hover = 0xFFFF0000; //鼠标移上去的颜色
        active = 0xFF00FF00; //鼠标按下去的颜色
    }
)

winform.show()
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Tooltip/tooltip.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Tooltip/tooltip.md')

