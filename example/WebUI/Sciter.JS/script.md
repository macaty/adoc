[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: script 接口

```aardio aardio
//script 接口
import win.ui;
/*DSG{{*/
var winform = win.form(text="script 接口";right=1014;bottom=523)
winform.add()
/*}}*/

import web.sciter;
web.sciter.script.gTest = "为所有网页自定义默认 JavaScript 全局变量";

//为所有网页添加初始化脚本
web.sciter.preloadScript(`globalThis.test=1;`)

//创建 Sciter 控件
var sciter = web.sciter( winform );

//为当前窗口添�?JavaScript 全局变量
sciter.script.aardio = {
    func = function(str){
         return "Hello, "+str+"!";
    }
}

sciter.html = /**
<body>
<button id="my-button">JavaSript 调用 aardio 函数 aardio.func("Sciter") </button>
<br> 请务必更�?web.sciter 扩展库到最新版�?br>
<span id="info"></span>
<script>

var button = document.getElementById("my-button");
button.addEventListener('click', () => {
    button.insertAdjacentHTML("afterEnd","<br>"+aardio.func("Sciter"))
})

window.jsFunction = function(param) {
  document.getElementById("info").innerText = param;
  return param;
}
</script>
</body>
**/

//访问当前窗口 JavaScript 全局变量
sciter.script.jsFunction("aardio 调用当前窗口 JavaScript 全局函数")

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/WebUI/Sciter.JS/script.md)

