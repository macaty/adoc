[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 浏览网页

```aardio aardio
//浏览网页
//请改用微软的 WebView2（也就是 aardio 标准库里�?web.view �?
import electron.app;
var theApp = electron.app(); // 创建electron进程,如果�?个参数为true，可以UTF8模式打开控制�?- 用于查看electron主进程输�?
//启动主进程的 main.js
theApp.jsMain =/**
    // 启动RPC服务允许aardio/electron互调函数,创建BrowserWindow主窗�?    const aardio = require('aardio')

    // 管理electron进程的生命周�?    const app = require('electron').app

    aardio.ready( win=> {
        win.removeMenu()

        win.on('closed', () => {

        })
    } )

    app.on('window-all-closed', () => {
        app.quit(); // 退出electron进程
    })
**/

//启用远程调试，并自动分配空闲不会冲突的端�?theApp.remoteDebuggingPort = 0;

//直接打开网页
theApp.start("http://bbs.aardio.com")

import web.socket.chrome;
var wsRemotetDebugging = web.socket.chrome();

//等待electron打开远程调试服务
wsRemotetDebugging.waitForConnected();

//使用远程调试端口控制网页
wsRemotetDebugging.Page.navigate( url = "http://bbs.aardio.com/forum.php?mod=viewthread&tid=11486&from=portal")

win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/WebUI/Electron/go.md)

