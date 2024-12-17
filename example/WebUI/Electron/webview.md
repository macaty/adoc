[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 妯℃嫙鑷姩鍖?
```aardio aardio
//妯℃嫙鑷姩鍖?//璇锋敼鐢ㄥ井杞殑 WebView2锛堜篃灏辨槸 aardio 鏍囧噯搴撻噷鐨?web.view 锛?import electron.app;
var app = electron.app();

//杩欐槸鍚姩electron涓昏繘绋嬬殑main.js
app.jsMain =/**
    const aardio = require('aardio')
    const app = require('electron').app

    app.on('window-all-closed', () => {
        app.quit();

    })
**/

//杩欐槸鍚姩涓昏繘绋嬬殑缃戦〉
app.html = /**
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <title>aardio宓屽叆electron婕旂ず</title>
  </head>

  <body>

   <webview id="view"  src="http://www.so.com"  autosize minwidth="576" minheight="1432"  style="display:inline-flex; width:100%; height:780px"></webview>

    <script type="text/javascript">

    //鑾峰彇宓屽叆鐨勬祻瑙堝櫒鎺т欢锛坵ebview)
    var webview = document.getElementById("view");

    //瀵煎叆aardio鏀寔
    aardio = require("aardio");
    aardio.on("executeJavaScript",(js)=>{

        //娉ㄥ叆JS鑴氭湰鍒版墦寮�鐨勮繙绋嬬綉椤?         webview.executeJavaScript(js);
    })

    //鍝嶅簲娴忚鍣ㄤ簨浠?    var domReady = function() {
        aardio.$domReady( webview.getURL() );
    }

    //鐩戝惉娴忚鍣ㄤ簨浠?    webview.addEventListener("dom-ready", domReady);
    </script>

</html>
**/

app.external = {

    $domReady = function($,url){

       //璋冪敤electron褰撳墠椤甸潰鐨?webview.executeJavaScript娉ㄥ叆骞舵墽琛宩s鑴氭湰
       app.xcall($,"executeJavaScript",`
       document.querySelector("#input").value = "https://electronjs.org/docs/api/webview-tag";
       document.querySelector("#search-button").click();
       `);
    }
}

app.start( "/res/main.aardio" );

win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/WebUI/Electron/webview.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/WebUI/Electron/webview.md')

