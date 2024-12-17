[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用chrome远程调试接口

```aardio aardio
//远程调试
import win.ui;
/*DSG{{*/
var winform = win.form(text="调用chrome远程调试接口";right=784;bottom=557;topmost=1)
winform.add(
btnConnect={cls="button";text="连接chrome";left=595;top=422;right=737;bottom=467;db=1;disabled=1;dr=1;z=4};
btnSend={cls="button";text="调用chrome打开网页";left=595;top=478;right=737;bottom=523;db=1;disabled=1;dr=1;z=3};
btnStartChrome={cls="button";text="启动chrome调试进程";left=201;top=364;right=368;bottom=409;db=1;dr=1;z=5};
buttonList={cls="button";text="获取可调试网页列�?;left=516;top=364;right=683;bottom=409;db=1;disabled=1;dr=1;z=7};
editPort={cls="edit";left=399;top=370;right=491;bottom=400;edge=1;multiline=1;z=6};
txtData={cls="edit";text="http://bbs.aardio.com/forum.php?mod=viewthread&tid=21977";left=32;top=481;right=585;bottom=520;db=1;dl=1;dr=1;edge=1;multiline=1;z=2};
txtMessage={cls="richedit";left=29;top=22;right=755;bottom=352;db=1;dl=1;dr=1;dt=1;edge=1;hscroll=1;multiline=1;vscroll=1;z=1};
txtWsUrl={cls="edit";left=35;top=425;right=588;bottom=464;edge=1;items={};z=8}
)
/*}}*/

import web.socket.chrome;
var ws = web.socket.chrome();

//打开连接触发的事�?ws.on("open",function(){
    winform.txtMessage.print("已打开连接");
    winform.btnSend.disabled = false;
})

ws.on("close",function(){
    winform.txtMessage.print("已关闭连�?);
    winform.btnStartChrome.disabledText = false;
});

ws.on("error",function(err){
    winform.txtMessage.print("出错�?,err);
});

//监听chrome事件
ws.on("Inspector.detached",function(param){
    winform.txtMessage.print("chrome已主动断开连接,原因�?,param);
})

ws.on("Network.requestWillBeSent",function(param){
    winform.txtMessage.print("准备发送请求：",param );
})

ws.on("Runtime.executionContextCreated",function(param){
    winform.txtMessage.print("Javascript executionContextId",param.context.id);
})

//调用chrome打开一个网�?winform.btnSend.oncommand = function(id,event){

    //允许触发Runtime.executionContextCreated
    ws.Runtime.enable();

    //允许触发Network.requestWillBeSent
    ws.Network.enable(
            maxTotalBufferSize = 10240;
    ).end = function(result,err){
        winform.txtMessage.print("调用Network.enable结果:",result)
    }

    ws.Page.navigate(
        url = winform.txtData.text;
    ).end = function(result,err){
        winform.txtMessage.print("调用返回参数",result)
    }
}

//连接chrome
winform.btnConnect.oncommand = function(id,event){
    ws.connect(winform.txtWsUrl.text);
}

import chrome.remote;
winform.btnStartChrome.oncommand = function(id,event){

    var cr = chrome.remote({
        //同一用户数据目录应当只启动一个开启远程调试端口的浏览器进�?        ["--user-data-dir"] = "%LocalAppData%\aardio\chrome.remote.userdata";
    })

    winform.editPort.text = cr.remoteDebuggingPort;
    if( cr.remoteDebuggingPort){
         winform.buttonList.disabled = false;
         winform.btnStartChrome.disabledText = "已启�?
    }
}

winform.buttonList.oncommand = function(id,event){
    winform.buttonList.disabled = true;
    thread.delay(100);

    var first;
    for id,title,wsUrl,devtoolsUrl in ws.eachDebuggingPage(winform.editPort.text) {
        winform.txtMessage.print(title);
        winform.txtMessage.print(devtoolsUrl);
        winform.txtMessage.print(wsUrl);
        winform.txtMessage.print();

        if(!first) {
            first = wsUrl;
            winform.btnConnect.disabled = false;
        }
    }

    winform.txtWsUrl.text = first : "";
    winform.buttonList.disabled = false;
}

winform.show()
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/WebUI/Chrome/remote.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/WebUI/Chrome/remote.md')

