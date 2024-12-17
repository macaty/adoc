[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 执行Ruby代码

```aardio aardio
//执行Ruby代码
import win.ui;
/*DSG{{*/
var winform = win.form(text="执行Ruby代码";right=759;bottom=469)
winform.add(
edit={cls="edit";left=26;top=16;right=737;bottom=435;db=1;dl=1;dr=1;dt=1;edge=1;multiline=1;z=1}
)
/*}}*/

import process.ruby;
var out = process.ruby.exec("puts '测试UTF-8'")
winform.edit.print(out);

var out = process.ruby.eval(`[1, 2, { name: "tanaka", age: 19 }]`)
winform.edit.print(out);

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Ruby/exec.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Ruby/exec.md')

