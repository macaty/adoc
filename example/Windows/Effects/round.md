[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 圆角无边框窗�?
```aardio aardio
import win.ui;
/*DSG{{*/
var winform = win.form(text="圆角无边框窗�?;right=759;bottom=469;border="none")
winform.add(
bkplus={cls="bkplus";left=-5;top=-3;right=763;bottom=38;bgcolor=12632256;dl=1;dr=1;dt=1;z=1}
)
/*}}*/

/*
创建圆角无边框窗口�?参数必须指定无边框窗口（也就是创建窗体的参数表里 border 属性为 "none"�?*/
import win.region.round;
win.region.round(winform,,,8,8);

//添加圆角阴影
import win.ui.shadow;
win.ui.shadow( winform,70,9,5,5);

//添加标题栏与拖动边框
import win.ui.simpleWindow;
win.ui.simpleWindow(winform);

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Effects/round.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Effects/round.md')

