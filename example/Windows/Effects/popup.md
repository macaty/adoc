[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 窗口程序 - 通知窗口

```aardio aardio
//窗口程序 - 通知窗口
import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio form";right=208;bottom=150;bgcolor=15780518;border="none";exmode="toolwindow";topmost=1)
winform.add(
button={cls="button";text="r";left=179;top=1;right=201;bottom=18;font=LOGFONT(name='Marlett';charset=2;weight=500);z=1};
static={cls="static";text="static";left=30;top=43;right=162;bottom=72;transparent=1;z=2}
)
/*}}*/

import win.util.popup

//使窗口在屏幕右下角弹�?pop = win.util.popup(winform)
pop.countdown=function(remaintime){
    winform.static.text = "剩余时间�? + remaintime  + "�?
}

winform.button.oncommand = function(id,event){
    winform.close();

}//endproc
winform.show(true)
win.loopMessage();
return winform;

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Effects/popup.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Effects/popup.md')
