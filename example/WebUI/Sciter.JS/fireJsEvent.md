[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: js 调用 aardio 自定义事�?
```aardio aardio
//触发 JS 事件
import win.ui;
/*DSG{{*/
var winform = win.form(text="js 调用 aardio 自定义事�?;right=1014;bottom=523;)
winform.add()
/*}}*/

import web.sciter;
var sciter = web.sciter( winform );

//�?web.sciter.behavior 名字空间添加自定�?behavior
namespace web.sciter.behavior.my.customEvent {

    /* 注意：自定义事件�?个回调参�?data 指向 behaviorParams.data 解包后的值，而不是behaviorParams.reason */
    onMyCustomEvent = function (scTarget,scOwner,data,behaviorParams) {

        import console
        console.log("onMyCustomEvent",data)
    }

    onButtonClick = function (scTarget,scOwner,reason,behaviorParams) {
        // 下面代码即可以触�?JS 事件，也可以触发 aardio 事件，sciter扩展库必须使用最新版�?        scOwner.fireEvent("onMyCustomEvent","这是data参数")
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
button.addEventListener('onMyCustomEvent', (event) => {
    event.currentTarget.innerHTML = "aardio触发了JS事件，收到data参数�? + event.data;
})
</script>
</body>
</html>
**/

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/WebUI/Sciter.JS/fireJsEvent.md)

