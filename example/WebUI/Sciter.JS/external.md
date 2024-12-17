[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: external 鎺ュ彛

```aardio aardio
//external 鎺ュ彛
import win.ui;
/*DSG{{*/
var winform = win.form(text="external 鎺ュ彛";right=1014;bottom=523)
winform.add()
/*}}*/

import web.sciter;

//鍙傛暟 @1 鎸囧畾宓屽叆缃戦〉鐨勭獥鍙ｏ紙鍙互鏄?winform 鎴?custom 鎺т欢瀵硅薄锛?var sciter = web.sciter( winform );

//涓嬮潰瀹氫箟鐨?external 瀵硅薄鍦?JavaScript 涓彲鐩存帴浣跨敤
sciter.external = {
    func = function(str){
         return "Hello, "+str+"!";
    }
}

sciter.html = /**
<body>
<button id="my-button">JavaSript 璋冪敤 aardio 鍑芥暟 external.func("Sciter") </button>
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

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/WebUI/Sciter.JS/external.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/WebUI/Sciter.JS/external.md')

