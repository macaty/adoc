[aardio 文档](../../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: / Go 通过 TCP 连接使用 JSON-RPC 交互

```aardio aardio
//aardio 调用 Go 语言 - RPC（TCP�?客户�?import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio / Go 通过 TCP 连接使用 JSON-RPC 交互";right=759;bottom=469)
winform.add(
button={cls="button";text="调用 Go 函数";left=382;top=389;right=678;bottom=427;db=1;dr=1;z=5};
edit={cls="edit";left=19;top=12;right=732;bottom=352;db=1;dl=1;dr=1;dt=1;edge=1;hscroll=1;multiline=1;vscroll=1;z=1};
editX={cls="edit";text="2";left=109;top=392;right=185;bottom=424;db=1;dl=1;edge=1;z=2};
editY={cls="edit";text="3";left=238;top=392;right=320;bottom=420;db=1;dl=1;edge=1;z=3};
static={cls="static";text="+";left=198;top=395;right=230;bottom=420;align="center";db=1;dl=1;transparent=1;z=4}
)
/*}}*/

if(!io.exist("/goRpc.exe"))  loadcodex("/JsonServer.aardio",true);

import process.rpc.tcpJsonClient;
var go,err  = process.rpc.tcpJsonClient("/goRpc.exe");

winform.onDestroy = function(){
    go.Calculator.Exit(0);//通知 Go 程序退�?}

winform.button.oncommand = function(id,event){

    //调用 Go 程序提供的函�?    var rep = go.Calculator.Add({
        X = tonumber(winform.editX.text);
        Y = tonumber(winform.editY.text);
    } )

    if( rep[["result"]] ){
        winform.edit.print( "调用成功", rep.result )
    }
    else {
        winform.edit.print( rep[["error"]] )
    }
}

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Go/RPC/TCP/JsonClient.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Go/RPC/TCP/JsonClient.md')
