[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 创建应用

```aardio aardio
//创建应用
//请改用微软的 WebView2（也就是 aardio 标准库里�?web.view ））

import electron.app;
var theApp = electron.app();

//这是启动electron主进程的main.js
theApp.jsMain =/**
    const aardio = require('aardio')  //启动RPC服务允许调aardio/electron互调函数,创建BrowserWindow主窗�?    const app = require('electron').app //管理electron进程的生命周�?
    /*
     * aardio-electron 主进程已准备就绪,
     * 主窗�?BrowserWindow)已创建触发此事件,
     * 可叠加注册多个回�?     */
    aardio.ready( win=> {
        //if( !aardio.studioInvoke  ){
            win.removeMenu()
        //}

       /*
        * 不建议用下面的代码打开调试工具,
        * 会有一些诡异的问题，例如不能输入中�?
        * 建议改为在aardio中调�?web.socket.chrome从外部打开调试工具.
        */
       // mainWindow.webContents.openDevTools ()
    } )

    app.on('window-all-closed', () => {
        app.quit();

    })
**/

// 可选在这里直接指定index.html的代码，实际开发请写到工程文件�?theApp.html = /**
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <title>aardio嵌入electron演示</title>
  </head>

  <body>

   <h2 onmousedown="aardio.hitCaption();return false;"
        style="-webkit-user-select: none;cursor:default;">按这里调用aardio.hitCaption()拖动窗口!</h2>

   <button onclick="aardio.exit();">点这里调用aardio关闭窗口</button> <br><br>

   <button id="aardio">点这里跟aardio互调一下函�?/button><br><br>

    <?
    response.write("在electron中执行aardio代码")
    ?>

    </body>

    <script type="text/javascript">

    /*导入aardio中的app.external 对象*/
    aardio = require("aardio");

    /*响应按钮点击事件*/
    document.querySelector("#aardio").onclick = function(e){

        //调用aardio中的函数,hello要调用的函数名字,后面可以跟任意个调用参数
        aardio.ex.hello( "你点击了" + e.target.innerHTML,1,2,3,"有几个参数写几个" )
            .then(
                function(message){
                    document.getElementById("aardio").innerText = "aardio返回�? + message;
                }
            )
    }

    /*响应aardio服务端发起的调查任务*/
    aardio.on("getUrl",function(){
        return document.location.href;
    });

    </script>

</html>
**/

/*
在下面的external对象中指定允许electron渲染进程中使用JS直接调用的函�?下面的external 会直接转换为js中的aardio对象，在JS中require('aardio')就可以使�?*/
theApp.external = {

    ex = {
        hello = function(...){
            win.msgbox( {...} ,"electron调用了aardio函数 hello " )
            return "electron,我是aardio.ex.hello，一起玩怎么样！�?
        }
    }

    exit = function(){
        theApp.close();//关闭主窗口，退出程�?    }

    //如果函数名第一个字符是$，则第一个回调参�?用于表示当前客户�?可作为xcall的参数使�?    $test = function($){
        theApp.xcall($,"js函数")
    }
}

theApp.onUrlReady = function(hSocket,url){
    // 加载一个页面完成都会触发这个事�?}

/*
启动electron,下面使用一个aardio表对象指定的启动参数�?在electron的主进程、渲染进程中都可以直接通过  aardio.startEnviron 访问�?*/
theApp.start(

    //electron打开的第一个页�?必须指定应用程序目录下的aardio代码文件
    indexUrl = "/res/main.aardio";

    //指定electron创建浏览器窗口的启动参数, 可以不写,aardio会自动给出正确参�?    browserWindow = {
        frame = false;
        webPreferences =  {
            nodeIntegration = true;
        }
    }

    /*
    可选用args字段指定Chrome命令行参�?
    必须在main.js中创建窗口以前就导入aardio模块才会生效
    */
    args ={

    }
);

//调查任务结束，JS代码汇报结果到这�?theApp.callback("getUrl",function(hSocket,result,err){
    win.msgbox(result,"打开了页�?)
})

theApp.onReady = function(){
    //对所有页面发起调查任�?
    theApp.survey("getUrl");
}

win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/WebUI/Electron/electron.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/WebUI/Electron/electron.md')

