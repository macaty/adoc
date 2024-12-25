[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: Sciter 脚本调用本地函数

```aardio aardio
//调用 JS 函数
import win.ui;
/*DSG{{*/
var winform = win.form(text="Sciter 脚本调用本地函数";right=1014;bottom=523;)
winform.add()
/*}}*/

import web.sciter;
var sciter = web.sciter( winform );

//JS 调试输出发送到到控制台，支�?JS �?console.log()
import web.sciter.debug;
sciter.attachEventHandler( web.sciter.debug );

//�?web.sciter.behavior 名字空间添加自定�?behavior
namespace web.sciter.behavior.button.command {

    /*
    ltOwner 参数是绑定behavior的节�?
    实际上也就是指定�?behavior:command 的节点对�?
    ltTarget 通常指的是实际触发事件的节点,
    或者根据不同的事件,ltTarget的意义有所不同
    */
    onButtonClick = function (scTarget,scOwner,reason,behaviorParams) {

        //调用节点的成员函数（ Javascript函数 �?        scOwner.customMethod("�?aardio 中调用节点上定义的JS函数：这是参�?)
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
        behavior:"button.command clickable";
    }
    </style>
</head>
<body>
<button id="my-button">请点击这�?/button> <span id="info"></span>
<script>

document.getElementById("my-button").customMethod = function(str){
     document.getElementById("info").innerText = str;
}

// window(或globalThis) 前缀这里可以省略
window.jsFunction = function(param) {
  document.getElementById("info").innerText = param;
  return param;
}

</script>
</body>
</html>
**/

//访问并操作页面节�?sciter.documentElement.querySelector("#info").insertAdjacentHTML("afterEnd","<br>测试insertAdjacentHTML")

sciter.eval(`
document.getElementById("info").innerText = "通过 sciter.eval 调用 javascript 函数 ";
`)

//参数"jsFunction"也可以写�?"globaThis.jsFunction"
sciter.call("jsFunction", "通过 sciter.call 调用 javascript 函数")

/*
更简单的方法是直接获�?Javascript 函数对象,
�?aardio 中能接收 Javascript 返回值的地方都支持直接返回Javascript 函数对象�?*/
var jsFunction = sciter.eval("jsFunction")

//如果要指定this参数，请使用 jsFunction.xcall(urlOrScriptName,jsThisObject,...)
jsFunction("直接�?aardio 中调�?Javascript 函数对象")

//也可以这样写:
//sciter.script.jsFunction("aardio 调用当前窗口 JavaScript 全局函数")

winform.show()
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/WebUI/Sciter.JS/callJs.md)

