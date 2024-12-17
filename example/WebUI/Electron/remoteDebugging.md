[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 在aardio中嵌入electron

```aardio aardio
//使用远程调试接口
//请改用微软的 WebView2（也就是 aardio 标准库里�?web.view �?import win.ui;
/*DSG{{*/
var winform = win.form(text="在aardio中嵌入electron";right=1276;bottom=767;clipch=1)
winform.add(
txtMessage={cls="richedit";left=1277;top=285;right=1758;bottom=799;bgcolor=16777215;db=1;dr=1;edge=1;link=1;multiline=1;vscroll=1;z=1}
)
/*}}*/

import electron.app;
var theApp = electron.app(winform);

//启动主进程的 main.js
theApp.jsMain =/**
    const aardio = require('aardio')  //启动RPC服务允许调aardio/electron互调函数,创建BrowserWindow主窗�?    const app = require('electron').app //管理electron进程的生命周�?
    app.on('window-all-closed', () => {
        app.quit();//退出electron进程
    })
**/

theApp.html = /**
<!DOCTYPE html>
<html>

  <head>
    <meta charset="UTF-8">
    <title>aardio嵌入electron演示</title>
    <script type="text/javascript">
        //导入aardio中的app.external 对象
         aardio = require("aardio");
    </script>
  </head>

  <body>

    <h2 onmousedown="aardio.hitCaption();return false;"
        style="-webkit-user-select: none;cursor:default;">按这里调用aardio.hitCaption()拖动窗口!</h2>

   <button onclick="aardio.quit();">点这里调用aardio关闭窗口</button> <br><br>

   <button onclick="aardio.showDevtools();">点这里打开chrome开发工�?/button><br><br>

   <button onclick="aardio.connectDebugging();">第一步：连接远程调试端口</button><br><br>
   <button onclick="aardio.testDebugging();">第二步：使用远程调试接口控制网页</button><br><br>
    </body>

</html>
**/

import web.socket.chrome;
var wsRemotetDebugging = web.socket.chrome();

//导出对象给electron
theApp.external = {
    showDevtools = function(){
        for id,title,wsUrl,devtoolsUrl in wsRemotetDebugging.eachDebuggingPage() {
            import process;
            process.execute(devtoolsUrl);
            break;
        }

    }
    connectDebugging = function(){
        //先让JS函数返回，推迟异步打开调试端口,试验这样比较流畅，反之偶尔会出现卡的现象
        winform.setTimeout( function(){
            if(!wsRemotetDebugging.connect()){
                winform.txtMessage.print(wsRemotetDebugging.getDebuggingInfo())
                winform.txtMessage.print("没有可用的远程调试接�?请先关闭连接到本页面的远程调试开发工�?注意远程调试接口只能被一个客户端独占");
            }
        });
    }
    testDebugging = function(){
        wsRemotetDebugging.Network.enable( maxTotalBufferSize = 10240;).end = function(result,err){
            winform.txtMessage.print("调用Network.enable结果:",result,err)
        }

        wsRemotetDebugging.Page.navigate( url = "http://bbs.aardio.com/forum.php?mod=viewthread&tid=11486&from=portal").end = function(result,err){
            winform.txtMessage.print("调用Page.navigate返回参数",err)
        }
    }

}

theApp.ws.onError = function(hSocket,err){
    winform.txtMessage.print("WebSocket服务端出错：",err );
}

//启用远程调试，并自动分配空闲不会冲突的端�?theApp.remoteDebuggingPort = 0;

//启动electron,也可以省略其他启动参�?直接指定要启动的网页地址
theApp.start("/res/main.aardio")

//监听chrome事件
wsRemotetDebugging.on("Inspector.detached",function(param){
    winform.txtMessage.print("chrome已主动断开连接,原因�?,param);
})

wsRemotetDebugging.on("Network.requestWillBeSent",function(param){
    winform.txtMessage.print("准备发送请求：",param );
})

//打开连接触发的事�?wsRemotetDebugging.on("open",function(){
    winform.txtMessage.print("已打开连接")
})

wsRemotetDebugging.on("close",function(){
    winform.txtMessage.print("已关闭连�?)
});

wsRemotetDebugging.on("error",function(err){
    winform.txtMessage.print("出错�?,err);
});

winform.txtMessage.orphanWindow()

winform.show()
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/WebUI/Electron/remoteDebugging.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/WebUI/Electron/remoteDebugging.md')

