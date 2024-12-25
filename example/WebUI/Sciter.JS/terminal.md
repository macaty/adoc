[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: ANSI 终端

```aardio aardio
//ANSI 终端
import win.ui;
/*DSG{{*/
var winform = win.form(text="ANSI 终端";right=759;bottom=469)
winform.add()
/*}}*/

import web.sciter;
var sciter = web.sciter(winform);

sciter.html = /**
<html>
    <head>
        <title>Test</title>
        <style></style>
        <script>

        const terminalView = document.$("terminal").terminal;
        writeTerminal = function(str){
            terminalView.write(str);
        }

        writeTerminal("hello world!");
        writeTerminal("\r\nAgain hello world!");

        writeTerminal("\x1B[1;31m This is red text \x1B[0m");

        </script>
    </head>
    <body>

     <terminal rows="24" columns="80" />

    </body>
</html>

**/

/*
调用 JavaScript 函数写入 ANSI 转义序列�?aardio �?'\e' 等价�?'\x1B'�?*/
sciter.script.writeTerminal('\e[42mHello\e[0m')

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/WebUI/Sciter.JS/terminal.md)

