[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: electron宓屽叆澶氫釜绐楀彛

```aardio aardio
//electron宓屽叆澶氫釜绐楀彛
//璇锋敼鐢ㄥ井杞殑 WebView2锛堜篃灏辨槸 aardio 鏍囧噯搴撻噷鐨?web.view 锛?import win.ui;
/*DSG{{*/
var winform = win.form(text="electron宓屽叆澶氫釜绐楀彛";right=1250;bottom=789;bgcolor=16777215)
winform.add(
custom={cls="custom";text="custom";left=29;top=14;right=518;bottom=779;bgcolor=16777215;db=1;dl=1;dt=1;z=1};
custom2={cls="custom";text="custom2";left=552;top=14;right=1196;bottom=779;bgcolor=16777215;db=1;dl=1;dr=1;dt=1;z=2}
)
/*}}*/

import electron.app;
//鍒涘缓绗竴涓猠lectron绐楀彛
var app = electron.app(winform.custom);
app.jsMain =/**

    //鍚姩RPC鏈嶅姟鍏佽璋僡ardio/electron浜掕皟鍑芥暟,鍒涘缓BrowserWindow涓荤獥鍙?    const aardio = require('aardio');
    aardio.ready( win=> {
        //if( !aardio.studioInvoke  ){
            win.removeMenu()
        //}
    })

    //绠＄悊electron杩涚▼鐨勭敓鍛藉懆鏈?    const app = require('electron').app;

    //鍦ㄦ墍鏈夌獥鍙ｅ叧闂椂閫�鍑篹lectron杩涚▼
    app.on('window-all-closed', () => app.quit() );
**/
app.start("http://bbs.aardio.com/forum.php?mod=viewthread&tid=12574&from=portal")

//鍒涘缓绗簩涓猠lectron绐楀彛
var app2 = electron.app(winform.custom2);
app2.jsMain =/**
    const aardio = require('aardio');
    const app = require('electron').app;
    aardio.ready( win=> {
        //if( !aardio.studioInvoke  ){
            win.removeMenu()
        //}
    })

    app.on('window-all-closed', () => app.quit() );
**/
app2.start("http://bbs.aardio.com/forum.php?mod=viewthread&tid=11486&from=portal")

winform.show()
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/WebUI/Electron/multiWindow.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/WebUI/Electron/multiWindow.md')

