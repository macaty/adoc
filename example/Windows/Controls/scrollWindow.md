[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 窗口滚动�?
```aardio aardio
//窗口滚动�?import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio form";right=759;bottom=469)
winform.add(
button={cls="button";text="button";left=118;top=73;right=260;bottom=120;ah=1;aw=1;z=1};
button2={cls="button";text="button2";left=107;top=397;right=356;bottom=530;ah=1;aw=1;z=2}
)
/*}}*/

import win.ui.scrollbar;
var vScrollBar = win.ui.scrollbar(winform,true);

vScrollBar.adjust = function( cx,cy,wParam ) {
    var scaleX,scaleY = winform.getScale();

    vScrollBar.line = 1 * scaleY;
    vScrollBar.setRange(1,100 * scaleY ,16);
};

winform.show()
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Controls/scrollWindow.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Controls/scrollWindow.md')

