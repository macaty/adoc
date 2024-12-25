[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: / Go 通过进程管道使用 JSON-RPC 交互

```aardio aardio
//aardio 调用 Go 语言 - RPC 客户�?import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio / Go 通过进程管道使用 JSON-RPC 交互";right=759;bottom=469)
winform.add(
button={cls="button";text="调用 Go 函数";left=382;top=389;right=678;bottom=427;db=1;dr=1;z=5};
edit={cls="edit";left=19;top=12;right=732;bottom=352;db=1;dl=1;dr=1;dt=1;edge=1;hscroll=1;multiline=1;vscroll=1;z=1};
editX={cls="edit";text="2";left=109;top=392;right=185;bottom=424;db=1;dl=1;edge=1;z=2};
editY={cls="edit";text="3";left=238;top=392;right=320;bottom=420;db=1;dl=1;edge=1;z=3};
static={cls="static";text="+";left=198;top=395;right=230;bottom=420;align="center";db=1;dl=1;transparent=1;z=4}
)
/*}}*/

if(!io.exist("/goRpc.exe"))  loadcodex("/JsonServer.aardio",true);

import process.rpc.jsonClient;

//可添加命令行参数，用法与 process，process.popen 相同。参考：范例 / 进程
var go,err = process.rpc.jsonClient("/goRpc.exe");

winform.button.oncommand = function(id,event){

    //调用 Go 程序提供的函�?    var rep,err = go.Calculator.Add({
        X = tonumber(winform.editX.text);
        Y = tonumber(winform.editY.text);
    } )

    if( rep[["result"]] ){
        winform.edit.print( `调用 go.Calculator.Add 成功，返回值：`, rep.result )
    }
    else{
        /*
        本地错误�?err 为错误信息，
        服务端错误则 err �?rep[["error"]] 对象�?JSON 文本格式
        */
        winform.edit.print(  err )
    }
}

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Go/RPC/JsonClient.md)

