[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: process.python - 指定启动参数

```aardio aardio
//指定启动参数
import win.ui;
/*DSG{{*/
var winform = win.form(text="process.python - 指定启动参数";right=759;bottom=469)
winform.add(
edit={cls="edit";left=16;top=22;right=722;bottom=420;edge=1;multiline=1;z=1}
)
/*}}*/

import process.python;

/*
执行 Python 代码
可指定一个或多个启动参数，也可以用一个字符串包含多个参数（空格分隔）
*/
var python = process.python.exec(`
import sys
print( sys.argv )
`,"参数1","参数2");

python.logResponse(winform.edit);

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python AnyVersion/argv.md)

