[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 文本框换行规�?
```aardio aardio
//文本框换行规�?//文本�? 编辑�? 富文本框, edit, richedit
import win.ui;
/*DSG{{*/
var winform = win.form(text="文本框换行规�?;right=314;bottom=342;border="dialog frame";max=false)
winform.add(
edit={cls="edit";text="edit";left=39;top=129;right=278;bottom=210;edge=1;multiline=1;z=1};
edit2={cls="edit";text="自动换行";left=39;top=29;right=278;bottom=110;autohscroll=false;edge=1;multiline=1;z=3};
richedit={cls="richedit";text="richedit";left=39;top=228;right=278;bottom=309;edge=1;multiline=1;z=2}
)
/*}}*/

winform.edit2.text = '
控件属性中，设置【垂直自动滚动】为true,设置【水平自动滚动】为false，即可支持自动换�?'

//EDIT控件的换行必须是'\r\n'
winform.edit.text = '第一行\r\n第二�?

//因为块注释用来表示字符串时，换行总是'\r\n'，所以可以这样赋�?winform.edit.text = /*
第一�?第二�?*/

//richedit控件要不要回车都可以，换行可以是'\n'，也可以�?\r\n'
winform.richedit.text = '第一行\n第二�?

//因为双引号（或反引号）包含字符串时，换行总是解析�?\n'，所以可以这样赋�?winform.richedit.text = "第一�?第二�?

winform.show()
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Edit/line.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Edit/line.md')

