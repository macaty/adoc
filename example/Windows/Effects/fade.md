[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 窗口程序 - 淡入淡出效果

```aardio aardio
//窗口程序 - 淡入淡出效果
import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio form";right=602;bottom=411;)
winform.add()
/*}}*/

import win.ui.fade;
win.ui.fade( winform );

win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Effects/fade.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Effects/fade.md')

