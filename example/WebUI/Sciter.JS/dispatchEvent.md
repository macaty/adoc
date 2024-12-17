[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: js 璋冪敤 aardio 鑷畾涔変簨浠?
```aardio aardio
//JS 瑙﹀彂鏈湴浜嬩欢
import win.ui;
/*DSG{{*/
var winform = win.form(text="js 璋冪敤 aardio 鑷畾涔変簨浠?;right=1014;bottom=523;)
winform.add()
/*}}*/

import web.sciter;
var sciter = web.sciter( winform );

namespace web.sciter.behavior.my.customEvent {

    /*
    鑷畾涔変簨浠剁3涓洖璋冨弬鏁?data 鎸囧悜 behaviorParams.data 瑙ｅ寘鍚庣殑鍊硷紝鑰屼笉鏄痓ehaviorParams.reason
    behaviorParams.data 鐨勫�煎湪 javascript 閲岀敤 event.data 鎴?event.detail 鎸囧畾銆?    dat
    */
    onMyCustomEvent = function (scTarget,scOwner,data,behaviorParams) {
        scOwner.value = "";
        scOwner.printf("aardio 鑷畾涔変簨浠?onMyCustomEvent 琚Е鍙?瑙﹀彂鍙傛暟:%s",data)
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
button.addEventListener('click', () => {
    var event = new CustomEvent("onMyCustomEvent", { detail :"鑷畾涔夊彧璇荤殑鑷畾涔夋暟鎹弬鏁帮紝鍙渷鐣?, bubbles:true});
    event.data = "鎸囧畾浜嬩欢鑷畾涔夋暟鎹弬鏁?; // aardio 閲?behaviorParams.data 浼樺厛鍙栬繖涓�硷紝鍙栦笉鍒板氨鍙?event.detail

    button.dispatchEvent(event, true);
})
</script>
</body>
</html>
**/

winform.show();
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/WebUI/Sciter.JS/dispatchEvent.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/WebUI/Sciter.JS/dispatchEvent.md')

