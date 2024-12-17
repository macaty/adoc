[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: script 鎺ュ彛

```aardio aardio
//script 鎺ュ彛
import win.ui;
/*DSG{{*/
var winform = win.form(text="script 鎺ュ彛";right=1014;bottom=523)
winform.add()
/*}}*/

import web.sciter;
web.sciter.script.gTest = "涓烘墍鏈夌綉椤佃嚜瀹氫箟榛樿 JavaScript 鍏ㄥ眬鍙橀噺";

//涓烘墍鏈夌綉椤垫坊鍔犲垵濮嬪寲鑴氭湰
web.sciter.preloadScript(`globalThis.test=1;`)

//鍒涘缓 Sciter 鎺т欢
var sciter = web.sciter( winform );

//涓哄綋鍓嶇獥鍙ｆ坊鍔?JavaScript 鍏ㄥ眬鍙橀噺
sciter.script.aardio = {
    func = function(str){
         return "Hello, "+str+"!";
    }
}

sciter.html = /**
<body>
<button id="my-button">JavaSript 璋冪敤 aardio 鍑芥暟 aardio.func("Sciter") </button>
<br> 璇峰姟蹇呮洿鏂?web.sciter 鎵╁睍搴撳埌鏈�鏂扮増鏈?br>
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

//璁块棶褰撳墠绐楀彛 JavaScript 鍏ㄥ眬鍙橀噺
sciter.script.jsFunction("aardio 璋冪敤褰撳墠绐楀彛 JavaScript 鍏ㄥ眬鍑芥暟")

winform.show();
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/WebUI/Sciter.JS/script.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/WebUI/Sciter.JS/script.md')

