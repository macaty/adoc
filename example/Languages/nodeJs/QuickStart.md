[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 璋冪敤 Node.js - 璁剧疆 startEnviron

```aardio aardio
//aardio 璋冪敤 Node.js - 璁剧疆 startEnviron
import console;
import nodeJs;

/*
JavaScript 蹇�熷叆闂細
https://quickref.me/zh-CN/docs/javascript.html
https://learnxinyminutes.com/docs/zh-cn/javascript-cn/
*/

var js = /******

console.log(process.argv.slice(2));

var startEnviron = require('startEnviron');
console.log(startEnviron.dest);

******/

//鑷姩鍒嗘瀽 JS 浠ｇ爜涓殑 require 璇彞骞跺畨瑁呬緷璧栨ā鍧?nodeJs.requireByJs(js);

//鎶婂璞′紶缁?node.js锛屽湪 JS 浠ｇ爜涓敤 require('startEnviron') 鑾峰彇銆?nodeJs.startEnviron({
    src:"浼犱釜瀛楃涓?,dest:{test:"宓屽鐨勫璞¤〃锛屼紶缁檔ode.js閮芥病闂",number:123, arr:{1,2,3} }
})

//鎵цJS锛岃繖閲屾寚瀹氱殑鍚姩鍙傛暟鍦?JS 浠ｇ爜涓彲鐢?process.argv 鑾峰彇銆?var prcs = nodeJs.exec(js,"args1","args2");
prcs.logResponse();

console.pause(true);

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/nodeJs/QuickStart.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/nodeJs/QuickStart.md')

