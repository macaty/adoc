[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 窗口程序 - 无边框窗�?
```aardio aardio
//窗口程序 - 无边框窗�?import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio form";right=759;bottom=469;bgcolor=16777215;border="none")
winform.add(
bk={cls="bk";left=-4;top=0;right=762;bottom=33;bgcolor=10789024;dl=1;dr=1;dt=1;z=1}
)
/*}}*/

/*
无边框窗口：指的是在窗体设计器中将窗体的边框(border) 属性设�?"none"�?这种窗口不再有边框、标题栏�?
注意隐藏标题栏、并将边框设�?"resizable"等不是无边框窗口�?这种效果在不同操作系统上显示效果都很差，要么是多出一圈，要么顶上多出一块�?不要这么做�?
无边框窗口只要使用下面的代码就可以在窗口周围添加阴影�?并同时使用阴影实现完美的可拖动改变大小效果（�?resizable 边框 ）�?
import win.ui.shadow;
win.ui.shadow(winform);

尤其是嵌入浏览器组件，直接使�?win.ui.resizeBorder 添加可拖动边框可能不起作用�?win.ui.shadow 可以通过阴影实现 win.ui.resizeBorder 的功能�?
如果只想添加阴影，不想支持可拖动边框，可以下面这样写�?
import win.ui.shadow;
win.ui.shadow(winform).setResizeBorder(false)

在无边框窗口上，可以自行实现标题栏按钮，调用以下函数模拟标题栏按钮消�?
winform.hitMax() //模拟点击最大化按钮
winform.hitMin() //模拟点击最小化按钮
winform.hitClose() //模拟点击关闭按钮
winform.hitCaption() //拖动标题�?*/

//下面的代码实现用鼠标左键按住窗口�?—�?可拖动改变窗口位�?winform.onMouseDown  = function(wParam,lParam){
    winform.hitCaption()
}

/*
标准库提供了以下的类可以直接在无边框窗口上创建虚拟的标题栏以及可拖动边框:

win.ui.simpleWindow 实现最普通的标题栏�?win.ui.simpleWindow2 实现的标题栏没有最大化按钮�?win.ui.simpleWindow3 标题栏使用分层窗口实现，并使�?orphanWindow 悬浮在父窗口上面�?*/

import win.ui.simpleWindow;
win.ui.simpleWindow(winform);//如果 winform 的最大化按钮设为隐藏(false)，则最大化按钮以及可拖动边框不会出现�?/*
win.ui.simpleWindow 默认创建的标题栏按钮是白色的�?所以建议在标题栏位置先放置一个背景贴图控�?bk 或�?bkplus，设置为深色背景�?并将�?bk �?bkplus 控件的固定边距属性设�?上边距、左边距、右边距固定边距�?true�?bk �?bkplus 控件并不会创建窗口，只是在父窗体上绘图，所以性能较好，也更适合在上面重叠放置其他控件�?*/

winform.show();
win.loopMessage();
return winform;

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Basics/frameless.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Basics/frameless.md')

