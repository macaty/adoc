[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 图像羽化边缘效果

```aardio aardio
//网络图像/羽化
import win.ui;
/*DSG{{*/
var winform = win.form(text="图像羽化边缘效果";right=759;bottom=469;bgcolor=16777215)
winform.add(
plus={cls="plus";left=28;top=32;right=730;bottom=397;repeat="scale";z=1}
)
/*}}*/

import inet.http;
import gdip.feather;
winform.plus.background = gdip.feather("http://pic23.photophoto.cn/20120429/0027011761472219_b.jpg",,0.55);

winform.show()
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Graphics/feather.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Graphics/feather.md')
