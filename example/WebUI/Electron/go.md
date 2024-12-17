[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 娴忚缃戦〉

```aardio aardio
//娴忚缃戦〉
//璇锋敼鐢ㄥ井杞殑 WebView2锛堜篃灏辨槸 aardio 鏍囧噯搴撻噷鐨?web.view 锛?
import electron.app;
var theApp = electron.app(); // 鍒涘缓electron杩涚▼,濡傛灉绗?涓弬鏁颁负true锛屽彲浠TF8妯″紡鎵撳紑鎺у埗鍙?- 鐢ㄤ簬鏌ョ湅electron涓昏繘绋嬭緭鍑?
//鍚姩涓昏繘绋嬬殑 main.js
theApp.jsMain =/**
    // 鍚姩RPC鏈嶅姟鍏佽aardio/electron浜掕皟鍑芥暟,鍒涘缓BrowserWindow涓荤獥鍙?    const aardio = require('aardio')

    // 绠＄悊electron杩涚▼鐨勭敓鍛藉懆鏈?    const app = require('electron').app

    aardio.ready( win=> {
        win.removeMenu()

        win.on('closed', () => {

        })
    } )

    app.on('window-all-closed', () => {
        app.quit(); // 閫�鍑篹lectron杩涚▼
    })
**/

//鍚敤杩滅▼璋冭瘯锛屽苟鑷姩鍒嗛厤绌洪棽涓嶄細鍐茬獊鐨勭鍙?theApp.remoteDebuggingPort = 0;

//鐩存帴鎵撳紑缃戦〉
theApp.start("http://bbs.aardio.com")

import web.socket.chrome;
var wsRemotetDebugging = web.socket.chrome();

//绛夊緟electron鎵撳紑杩滅▼璋冭瘯鏈嶅姟
wsRemotetDebugging.waitForConnected();

//浣跨敤杩滅▼璋冭瘯绔彛鎺у埗缃戦〉
wsRemotetDebugging.Page.navigate( url = "http://bbs.aardio.com/forum.php?mod=viewthread&tid=11486&from=portal")

win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/WebUI/Electron/go.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/WebUI/Electron/go.md')

