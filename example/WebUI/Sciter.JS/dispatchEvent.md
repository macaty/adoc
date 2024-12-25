[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: js 调用 aardio 自定义事�?
```aardio aardio
//JS 触发本地事件
import win.ui;
/*DSG{{*/
var winform = win.form(text="js 调用 aardio 自定义事�?;right=1014;bottom=523;)
winform.add()
/*}}*/

import web.sciter;
var sciter = web.sciter( winform );

namespace web.sciter.behavior.my.customEvent {

    /*
    自定义事件第3个回调参�?data 指向 behaviorParams.data 解包后的值，而不是behaviorParams.reason
    behaviorParams.data 的值在 javascript 里用 event.data �?event.detail 指定�?    dat
    */
    onMyCustomEvent = function (scTarget,scOwner,data,behaviorParams) {
        scOwner.value = "";
        scOwner.printf("aardio 自定义事�?onMyCustomEvent 被触�?触发参数:%s",data)
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
<button id="my-button">请点击这里调�?behavior 里定义的 aardio函数：onMyCustomEvent </button>
<script>
var button = document.getElementById("my-button");
button.addEventListener('click', () => {
    var event = new CustomEvent("onMyCustomEvent", { detail :"自定义只读的自定义数据参数，可省�?, bubbles:true});
    event.data = "指定事件自定义数据参�?; // aardio �?behaviorParams.data 优先取这个值，取不到就�?event.detail

    button.dispatchEvent(event, true);
})
</script>
</body>
</html>
**/

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/WebUI/Sciter.JS/dispatchEvent.md)

