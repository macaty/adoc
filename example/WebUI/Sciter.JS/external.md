[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: external 接口

```aardio aardio
//external 接口
import win.ui;
/*DSG{{*/
var winform = win.form(text="external 接口";right=1014;bottom=523)
winform.add()
/*}}*/

import web.sciter;

//参数 @1 指定嵌入网页的窗口（可以�?winform �?custom 控件对象�?var sciter = web.sciter( winform );

//下面定义�?external 对象�?JavaScript 中可直接使用
sciter.external = {
    func = function(str){
         return "Hello, "+str+"!";
    }
}

sciter.html = /**
<body>
<button id="my-button">JavaSript 调用 aardio 函数 external.func("Sciter") </button>
<script>

var button = document.getElementById("my-button");
button.addEventListener('click', () => {

    //https://github.com/c-smile/sciter-js-sdk/blob/main/docs/md/Window.md
    //https://sciter.com/tutorials/reactor-jsx
    Window.this.modal(<info>{ external.func("Sciter")}</info>);
})

</script>
</body>
**/

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/WebUI/Sciter.JS/external.md)

