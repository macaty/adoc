[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 屏幕任意坐标显示提示

```aardio aardio
//任意坐标提示
import win.ui;
/*DSG{{*/
var winform = win.form(text="屏幕任意坐标显示提示";right=759;bottom=469)
winform.add(
btnPopup={cls="button";text="显示简单提�?;left=462;top=351;right=707;bottom=421;color=14120960;font=LOGFONT(h=-14);note="只需要一句代�?;z=1}
)
/*}}*/

import winex.tooltip;

/*
不指定最后一个超时参数，则鼠标点击任意位置关闭�?参数 @2,@3 指定显示提示�?x,y 坐标，不指定坐标则取鼠标当前坐标�?参数 @1 指定要显示的内容，如果包含换行，则第一行显示为标题（同时显示关闭按钮）�?*/
winex.tooltip.balloon('可选在换行符前指定标题\n屏幕任意坐标显示提示',100,100,2000/*超时毫秒�?/);

winform.btnPopup.oncommand = function(id,event){

    /*
    用法�?winex.tooltip.balloon() 相同，但无汽泡样式�?    */
    winex.tooltip.popup('这是提示内容',100,100);
}

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Tooltip/winex.tooltip.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Tooltip/winex.tooltip.md')

