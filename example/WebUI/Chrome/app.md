[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: app 应用

```aardio aardio
//app 应用
import chrome.app;

//调用系统 Edge（Chromium）、Chrome、Supermium �?Chromium 内核浏览器写软件界面
//XP、Win7 系统可使�?Supermium  以支持新 Chromium 内核�?var theApp  = chrome.app();

//指定允许chrome中使用JS直接调用的函�?theApp.external = {

    test = function(){
       theApp.msgbox("页面js调用了aardio函数");
    }

    //如果函数名第一个字符是$，则第一个回调参�?用于表示当前客户�?可作为xcall的参数使�?    $test = function($){
        theApp.xcall($,"js函数")
    }

    tag = function(strs,...){
        var args = {...}
        for(i=#args;1;-1){
            table.insert(strs,args[i],i+1);
        }

        strs = string.join(strs);
        return strs;
    }
}

//虚拟一个服务端页面，如果在﻿工程里直接添加一个文件到﻿工程就可以�?//因为 /res/ 已设�?theApp.http.documentBase，这里不用再�?"/res/index.aardio"
theApp.httpHandler["/index.aardio" ] = /***
    <script src="/aardio.js"></script>
    <title>aardio调用chrome</title>
    <body>
        <button onclick="aardio.test()">调用aardio函数</button>

        <pre>
        如果使用webpack等构建前端项目�?        前端﻿工程中直接执行 npm i aardio 安装aardio.js即可�?        然后JS中直接调�?import aardio from 'aardio' 引入aardi.js
        即可使用aardio对象( 已经做好了智能提示，可在d.ts中添加更多external接口函数 )

        chrome.app支持系统已安装的Chrome、或其他兼容Chrome启动参数的浏览器�?        并且可以支持即将成为WIN7,WIN10默认系统浏览器的Edge(Chromium�?
        </pre>

        <script>
        let $ = aardio.tag;
        $`abc${123}ddd${456}`.then( v=> document.body.insertAdjacentHTML("beforeEnd","aardio 解析�?JS 模板字符�?"+v)  )
        </script>
    <body>
***/

//此函数参数指定的回调函数会在网页端准备就绪后执行
theApp.indexReady(
    function($){ //参数 $ 表示当前连接�?aardio 的网页客户端
        theApp.doScript($,`
        alert("�?aardio 里执行了 JavaScript 代码")
        `)
    }
)

//可选在调用 start 函数前用 theApp.setPos �?theApp.center 调整窗口位置
theApp.center();

/*
正式启动 Chrome 进程�?如果文件名为 index.html �?index.aardio，目�?"/res/" 会自动设�?theApp.http.documentBase�?之后网页访问 "/index.aardio" 会自动转�?"/res/index.aardio" �?*/
theApp.start("/res/index.aardio");

//网页中可以调�?aardio.quit() 退�?也可以直接关�?Chrome 窗口退�?win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/WebUI/Chrome/app.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/WebUI/Chrome/app.md')

