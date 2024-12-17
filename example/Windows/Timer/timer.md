[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 可启用、禁用、调整时间隔的定时管理器

```aardio aardio
//窗口程序 - 定时管理�?import win.ui;
/*DSG{{*/
var winform = win.form(text="可启用、禁用、调整时间隔的定时管理器";right=412;bottom=198;)
winform.add(
btnDisable={cls="button";text="禁用定时�?;left=221;top=62;right=375;bottom=97;z=3};
btnEnable={cls="button";text="启用定时�?;left=36;top=63;right=190;bottom=98;z=1};
lbIntervalMax={cls="static";text="间隔1000毫秒";left=286;top=121;right=373;bottom=135;align="right";transparent=1;z=6};
lbIntervalMin={cls="static";text="间隔1毫秒";left=40;top=120;right=103;bottom=135;transparent=1;z=5};
static={cls="static";text="...........";left=39;top=19;right=375;bottom=50;center=1;nWrap=1;transparent=1;z=2};
trackbar={cls="trackbar";left=26;top=136;right=383;bottom=166;max=1000;min=1;z=4}
)
/*}}*/

import win.timer
var timer = win.timer( winform );
timer.onTimer = function(hwnd,msg,id,tick){
    winform.static.text = time.tick();
}

winform.btnDisable.oncommand = function(id,event){
    timer.disable()
}

winform.btnEnable.oncommand = function(id,event){
    timer.enable();
}

winform.trackbar.setFrequency(10)
winform.trackbar.oncommand = function(id,event,pos){
    if( pos ){
         timer.setInterval(pos)
    }
}

winform.show()
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Timer/timer.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Timer/timer.md')

