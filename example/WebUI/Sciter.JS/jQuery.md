[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: jQuery 娴嬭瘯

```aardio aardio
//jQuery
import win.ui;
/*DSG{{*/
var winform = win.form(text="jQuery 娴嬭瘯";right=461;bottom=289;scroll=1)
winform.add()
/*}}*/

import web.sciter;
var wb = web.sciter(winform)

import process;
wb.onHyperlinkClick = function (scTarget,scOwner) {
    process.openUrl(scTarget.href);
}

/*
jQuery 蹇�熷叆闂?https://quickref.me/jquery
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
    娴嬭瘯 jQuery
    </button>

    <script>
    $("button#btn").click(
        function(){
            $("div#idTest2").html("<a href='https://api.jquery.com/' target='_blank'>鎵撳紑 jQuery 鏂囨。</a>")
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

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/WebUI/Sciter.JS/jQuery.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/WebUI/Sciter.JS/jQuery.md')

