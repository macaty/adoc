[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: process.python - 入门

```aardio aardio
//入门
import win.ui;
/*DSG{{*/
var winform = win.form(text="process.python - 入门";right=759;bottom=469)
winform.add(
edit={cls="edit";left=16;top=22;right=722;bottom=420;edge=1;multiline=1;z=1}
)
/*}}*/

import process.python;
/*
如果指定 process.python.path = "python.exe"
则调用系统安装的 Python，没安装会自动下载安装，
否则调用绿色嵌入�?Python ，没下载也会自动下载�?*/

/*
执行 Python 代码，支持任意版�?python ( 支持 64�?Python )�?调用 32 / 64 �?python.exe 都可以在发布 aardio 程序时打包为独立 EXE 文件�?
参数也可以是�?.py, *.aardio 文件路径，支持内存加载资源文件）
如果 Python 代码开始为 aardio 模板标记，则启用模板语法�?https://www.aardio.com/zh-cn/doc/language-reference/templating/syntax.html
*/
var python = process.python.exec(`
?>import json
str = json.dumps(['foo', "<?=
time() //可使用模板语法嵌�?aardio  代码
?>",{'bar': ('baz', None, 1.0, 2)}])

# print 写到进程标准输出，在 aardio 中可以读�?print( str )
`);

/*
这里�?python 对象就是进程管道�?process.popen ）对象�?下面�?python.json 读取进程输出的下一�?JSON 并转换为 aardio 对象，忽略非 JSON 输出�?读取其他数据可以改为 readAll() �?read() 函数�?*/
var info,err = python.json();

winform.edit.print(info || err);

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python AnyVersion/QuickStart.md)

