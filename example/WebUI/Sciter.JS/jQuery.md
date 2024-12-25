[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: jQuery 测试

```aardio aardio
//jQuery
import win.ui;
/*DSG{{*/
var winform = win.form(text="jQuery 测试";right=461;bottom=289;scroll=1)
winform.add()
/*}}*/

import web.sciter;
var wb = web.sciter(winform)

import process;
wb.onHyperlinkClick = function (scTarget,scOwner) {
    process.openUrl(scTarget.href);
}

/*
jQuery 快速入�?https://quickref.me/jquery
https://learnxinyminutes.com/docs/zh-cn/jquery-cn/
*/

wb.html = /**
<!doctype html>
<html>
<head>
    <meta charset="utf-8">
    <script src="https://lib.baomitu.com/jquery/3.5.1/jquery.min.js"></script>
</head>
<body>
    <div id="idTest2" class="style2"> </div>
    <br>
    <button id="btn">
    测试 jQuery
    </button>

    <script>
    $("button#btn").click(
        function(){
            $("div#idTest2").html("<a href='https://api.jquery.com/' target='_blank'>打开 jQuery 文档</a>")
            $("div#idTest2").fadeIn( "slow" );
        }
    )
    </script>
</body>
</html>
**/

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/WebUI/Sciter.JS/jQuery.md)

