[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: process.python - 切换 Python 版本

```aardio aardio
//切换版本
import win.ui;
/*DSG{{*/
var winform = win.form(text="process.python - 切换 Python 版本";right=759;bottom=469)
winform.add(
edit={cls="edit";left=16;top=22;right=722;bottom=420;edge=1;multiline=1;z=1}
)
/*}}*/

import process.python;

//可选自定义 python.exe 路径�?//默认�?"/py/python.exe"，推荐放在这个目录�?//如果设为 "python.exe" 则调用系统安装的 python
process.python.path = "/py/python.exe";

//如果 python.exe 不存在，aardio 会自动下�?python
//可在下面指定需要下载的默认版本号�?process.python.version = "3.8.10";

//执行 Python 代码�?var python = process.python.exec(`
import sys
print( sys.version )
`);

//此函数会等待进程结束，但不会阻塞当前线程窗口消息�?//读取进程输出（包含错误输出），错误输出（第二个返回值）
var out,err = python.readAll();

//在文本框中显�?winform.edit.text = out;

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python AnyVersion/version.md)

