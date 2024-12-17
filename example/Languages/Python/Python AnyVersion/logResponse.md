[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: process.python - 入门

```aardio aardio
//异步回显
import win.ui;
/*DSG{{*/
var winform = win.form(text="process.python - 入门";right=759;bottom=469)
winform.add(
edit={cls="edit";left=16;top=22;right=722;bottom=420;edge=1;multiline=1;z=1}
)
/*}}*/

import process.python;

/*
执行 Python 代码�?如果 Python 代码开始为 aardio 模板标记，则启用模板语法�?https://www.aardio.com/zh-cn/doc/language-reference/templating/syntax.html
*/
var python = process.python.exec(`?>
import sys
import time

# print 写到进程标准输出，在 aardio 中可以读�?print( "这是 Python 代码输出的字符串 " )

sys.stdout.flush()
time.sleep( 1 )

print( "这是 Python 代码输出的字符串  " )
`);

/*
此函数参数如果指定文本框作为回显对象，则异步回显进程输出�?启用异步回显示，函数不会阻塞，而是继续向后执行�?*/
python.logResponse( winform.edit );
/*
参数也可以是回显函数，详�?process.popen 文档�?参数是回显函数而不是回显控件，则阻塞函数直到被调用进程退�?如果不指定参数，且导入了 console 库，则默认回显到控制台�?*/

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python AnyVersion/logResponse.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python AnyVersion/logResponse.md')

