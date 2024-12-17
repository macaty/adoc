[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 显示部分网页

```aardio aardio
//显示部分网页
import win.ui;
/*DSG{{*/
var winform = win.form(bottom=518;text="aardio form";border="resizable";right=831 )
winform.add(
staticParent={ dl=1;bottom=270;right=525;left=34;dt=1;top=20;z=1;text="PIC";edge=1;cls="static" };
static={ dl=1;bottom=209;right=425;left=107;dt=1;top=75;z=2;text="static";edge=1;cls="static" }
)
/*}}*/

import web.form;
var wb = web.form(winform.static, 0x4/*_UIFLAG_NO3DBORDER*/ | 0x8/*_UIFLAG_SCROLL_NO*/);
wb.go("http://www.aardio.com");

winform.static.setPos(-80,-200,1000,1000)
winform.static.setParent( winform.staticParent );

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/WebUI/web.form/Automation/crop.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/WebUI/web.form/Automation/crop.md')

