[aardio 鏂囨。](../../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: / Go 閫氳繃杩涚▼绠￠亾浣跨敤 JSON-RPC 浜や簰

```aardio aardio
//aardio 璋冪敤 Go 璇█ - RPC 瀹㈡埛绔?import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio / Go 閫氳繃杩涚▼绠￠亾浣跨敤 JSON-RPC 浜や簰";right=759;bottom=469)
winform.add(
button={cls="button";text="璋冪敤 Go 鍑芥暟";left=382;top=389;right=678;bottom=427;db=1;dr=1;z=5};
edit={cls="edit";left=19;top=12;right=732;bottom=352;db=1;dl=1;dr=1;dt=1;edge=1;hscroll=1;multiline=1;vscroll=1;z=1};
editX={cls="edit";text="2";left=109;top=392;right=185;bottom=424;db=1;dl=1;edge=1;z=2};
editY={cls="edit";text="3";left=238;top=392;right=320;bottom=420;db=1;dl=1;edge=1;z=3};
static={cls="static";text="+";left=198;top=395;right=230;bottom=420;align="center";db=1;dl=1;transparent=1;z=4}
)
/*}}*/

if(!io.exist("/goRpc.exe"))  loadcodex("/JsonServer.aardio",true);

import process.rpc.jsonClient;

//鍙坊鍔犲懡浠よ鍙傛暟锛岀敤娉曚笌 process锛宲rocess.popen 鐩稿悓銆傚弬鑰冿細鑼冧緥 / 杩涚▼
var go,err = process.rpc.jsonClient("/goRpc.exe");

winform.button.oncommand = function(id,event){

    //璋冪敤 Go 绋嬪簭鎻愪緵鐨勫嚱鏁?    var rep,err = go.Calculator.Add({
        X = tonumber(winform.editX.text);
        Y = tonumber(winform.editY.text);
    } )

    if( rep[["result"]] ){
        winform.edit.print( `璋冪敤 go.Calculator.Add 鎴愬姛锛岃繑鍥炲�硷細`, rep.result )
    }
    else{
        /*
        鏈湴閿欒鍒?err 涓洪敊璇俊鎭紝
        鏈嶅姟绔敊璇垯 err 涓?rep[["error"]] 瀵硅薄鐨?JSON 鏂囨湰鏍煎紡
        */
        winform.edit.print(  err )
    }
}

winform.show();
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Go/RPC/JsonClient.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Go/RPC/JsonClient.md')

