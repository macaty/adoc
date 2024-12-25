[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: RPC 服务�?- 支持任意本地网页调用 aardio 函数

```aardio aardio
//Node.js 回调 aardio
import win.ui;
/*DSG{{*/
var winform = win.form(text="RPC 服务�?- 支持任意本地网页调用 aardio 函数";right=759;bottom=469)
winform.add(
button={cls="button";text="调用 Node.js 函数";left=480;top=410;right=630;bottom=449;db=1;dr=1;z=2};
edit={cls="richedit";left=23;top=24;right=730;bottom=380;db=1;dl=1;dr=1;dt=1;edge=1;hscroll=1;multiline=1;vscroll=1;z=1}
)
/*}}*/

winform.edit.print("正在启动 Node.js");
winform.show();

import web.rpc.externalServer;
var externalServer = web.rpc.externalServer();

//定义允许 Node.js 调用�?aardio 函数
externalServer.external = {
    test = function(...){
        winform.button.disabled = false;
        winform.edit.print("external.test 被调�?,...)
        return "aardio 函数返回的�?
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

//启动 aardio-rpc 服务�?externalServer.start();

winform.button.disabled = true;
winform.button.oncommand = function(id,event){
    externalServer.publish("testJs",1,2,3);
}

import nodeJs;

var js  =/*
var aardio = require('aardio')
aardio.test(123).then( v=>{ console.log(v) } );

aardio.on("testJs",function(...values){
    console.log("Node.js 函数 testJs 被调�?,...values)
})

//�?aardio 解析模板字符�?const $ = aardio.tag;
$`abc${123}ddd${456}`.then( v=> console.log("模板字符�?",v)  )
*/

//自动安装 JS 代码中引用的模块，如果已经安装了模块，这句代码会自动忽略不执�?nodeJs.prequireByJs(winform.edit,js);

//运行 Node.js 代码，如果改�?nodeJs.startRpc() �?JS �?console.log 不可�?var node = nodeJs.exec(js);

//窗体退出时结束 nodeJs 进程
winform.onDestroy = function(){
    node.ctrlEvent(0)
}

//�?Node.js 进程输出显示到文本框，不会阻塞进�?node.logResponse(winform.edit);

win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/nodeJs/external.md)

