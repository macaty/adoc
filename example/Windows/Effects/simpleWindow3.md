[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 窗口程序 - 透明渐变标题�?
```aardio aardio
//窗口程序 - 透明渐变标题�?import win.ui;
/*DSG{{*/
var winform = win.form(text="透明渐变标题�?;right=759;bottom=469;border="none")
winform.add()
/*}}*/

import inet.http;
winform.image = "http://pic23.photophoto.cn/20120429/0027011761472219_b.jpg";

import win.ui.simpleWindow3;
win.ui.simpleWindow3(winform)

winform.show()
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Effects/simpleWindow3.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Effects/simpleWindow3.md')

