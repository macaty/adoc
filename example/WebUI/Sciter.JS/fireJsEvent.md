[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: js 璋冪敤 aardio 鑷畾涔変簨浠?
```aardio aardio
//瑙﹀彂 JS 浜嬩欢
import win.ui;
/*DSG{{*/
var winform = win.form(text="js 璋冪敤 aardio 鑷畾涔変簨浠?;right=1014;bottom=523;)
winform.add()
/*}}*/

import web.sciter;
var sciter = web.sciter( winform );

//鍦?web.sciter.behavior 鍚嶅瓧绌洪棿娣诲姞鑷畾涔?behavior
namespace web.sciter.behavior.my.customEvent {

    /* 娉ㄦ剰锛氳嚜瀹氫箟浜嬩欢绗?涓洖璋冨弬鏁?data 鎸囧悜 behaviorParams.data 瑙ｅ寘鍚庣殑鍊硷紝鑰屼笉鏄痓ehaviorParams.reason */
    onMyCustomEvent = function (scTarget,scOwner,data,behaviorParams) {

        import console
        console.log("onMyCustomEvent",data)
    }

    onButtonClick = function (scTarget,scOwner,reason,behaviorParams) {
        // 涓嬮潰浠ｇ爜鍗冲彲浠ヨЕ鍙?JS 浜嬩欢锛屼篃鍙互瑙﹀彂 aardio 浜嬩欢锛宻citer鎵╁睍搴撳繀椤讳娇鐢ㄦ渶鏂扮増鏈?        scOwner.fireEvent("onMyCustomEvent","杩欐槸data鍙傛暟")
    }
}

sciter.html = /**
<!doctype html>
<html>
<head>
    <META http-equiv="Content-Type" content="text/html; charset=utf-8">
    <style type="text/css">
    html,body{ height:100%; margin:50; }

    #my-button{
        behavior:"my.customEvent clickable";
    }
    </style>
</head>
<body>
<button id="my-button">璇风偣鍑昏繖閲岃皟鐢?behavior 閲屽畾涔夌殑 aardio鍑芥暟锛歰nMyCustomEvent </button>
<script>
var button = document.getElementById("my-button");
button.addEventListener('onMyCustomEvent', (event) => {
    event.currentTarget.innerHTML = "aardio瑙﹀彂浜咼S浜嬩欢锛屾敹鍒癲ata鍙傛暟锛? + event.data;
})
</script>
</body>
</html>
**/

winform.show();
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/WebUI/Sciter.JS/fireJsEvent.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/WebUI/Sciter.JS/fireJsEvent.md')

