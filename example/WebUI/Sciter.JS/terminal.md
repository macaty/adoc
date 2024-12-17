[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: ANSI 缁堢

```aardio aardio
//ANSI 缁堢
import win.ui;
/*DSG{{*/
var winform = win.form(text="ANSI 缁堢";right=759;bottom=469)
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
璋冪敤 JavaScript 鍑芥暟鍐欏叆 ANSI 杞箟搴忓垪銆?aardio 涓?'\e' 绛変环浜?'\x1B'銆?*/
sciter.script.writeTerminal('\e[42mHello\e[0m')

winform.show();
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/WebUI/Sciter.JS/terminal.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/WebUI/Sciter.JS/terminal.md')

