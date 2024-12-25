[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 模拟自动�?
```aardio aardio
//模拟自动�?//请改用微软的 WebView2（也就是 aardio 标准库里�?web.view �?import electron.app;
var app = electron.app();

//这是启动electron主进程的main.js
app.jsMain =/**
    const aardio = require('aardio')
    const app = require('electron').app

    app.on('window-all-closed', () => {
        app.quit();

    })
**/

//这是启动主进程的网页
app.html = /**
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <title>aardio嵌入electron演示</title>
  </head>

  <body>

   <webview id="view"  src="http://www.so.com"  autosize minwidth="576" minheight="1432"  style="display:inline-flex; width:100%; height:780px"></webview>

    <script type="text/javascript">

    //获取嵌入的浏览器控件（webview)
    var webview = document.getElementById("view");

    //导入aardio支持
    aardio = require("aardio");
    aardio.on("executeJavaScript",(js)=>{

        //注入JS脚本到打开的远程网�?         webview.executeJavaScript(js);
    })

    //响应浏览器事�?    var domReady = function() {
        aardio.$domReady( webview.getURL() );
    }

    //监听浏览器事�?    webview.addEventListener("dom-ready", domReady);
    </script>

</html>
**/

app.external = {

    $domReady = function($,url){

       //调用electron当前页面�?webview.executeJavaScript注入并执行js脚本
       app.xcall($,"executeJavaScript",`
       document.querySelector("#input").value = "https://electronjs.org/docs/api/webview-tag";
       document.querySelector("#search-button").click();
       `);
    }
}

app.start( "/res/main.aardio" );

win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/WebUI/Electron/webview.md)

