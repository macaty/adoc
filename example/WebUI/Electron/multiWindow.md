[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: electron嵌入多个窗口

```aardio aardio
//electron嵌入多个窗口
//请改用微软的 WebView2（也就是 aardio 标准库里�?web.view �?import win.ui;
/*DSG{{*/
var winform = win.form(text="electron嵌入多个窗口";right=1250;bottom=789;bgcolor=16777215)
winform.add(
custom={cls="custom";text="custom";left=29;top=14;right=518;bottom=779;bgcolor=16777215;db=1;dl=1;dt=1;z=1};
custom2={cls="custom";text="custom2";left=552;top=14;right=1196;bottom=779;bgcolor=16777215;db=1;dl=1;dr=1;dt=1;z=2}
)
/*}}*/

import electron.app;
//创建第一个electron窗口
var app = electron.app(winform.custom);
app.jsMain =/**

    //启动RPC服务允许调aardio/electron互调函数,创建BrowserWindow主窗�?    const aardio = require('aardio');
    aardio.ready( win=> {
        //if( !aardio.studioInvoke  ){
            win.removeMenu()
        //}
    })

    //管理electron进程的生命周�?    const app = require('electron').app;

    //在所有窗口关闭时退出electron进程
    app.on('window-all-closed', () => app.quit() );
**/
app.start("http://bbs.aardio.com/forum.php?mod=viewthread&tid=12574&from=portal")

//创建第二个electron窗口
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

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/WebUI/Electron/multiWindow.md)

