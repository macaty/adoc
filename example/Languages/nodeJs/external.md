[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: RPC 鏈嶅姟绔?- 鏀寔浠绘剰鏈湴缃戦〉璋冪敤 aardio 鍑芥暟

```aardio aardio
//Node.js 鍥炶皟 aardio
import win.ui;
/*DSG{{*/
var winform = win.form(text="RPC 鏈嶅姟绔?- 鏀寔浠绘剰鏈湴缃戦〉璋冪敤 aardio 鍑芥暟";right=759;bottom=469)
winform.add(
button={cls="button";text="璋冪敤 Node.js 鍑芥暟";left=480;top=410;right=630;bottom=449;db=1;dr=1;z=2};
edit={cls="richedit";left=23;top=24;right=730;bottom=380;db=1;dl=1;dr=1;dt=1;edge=1;hscroll=1;multiline=1;vscroll=1;z=1}
)
/*}}*/

winform.edit.print("姝ｅ湪鍚姩 Node.js");
winform.show();

import web.rpc.externalServer;
var externalServer = web.rpc.externalServer();

//瀹氫箟鍏佽 Node.js 璋冪敤鐨?aardio 鍑芥暟
externalServer.external = {
    test = function(...){
        winform.button.disabled = false;
        winform.edit.print("external.test 琚皟鐢?,...)
        return "aardio 鍑芥暟杩斿洖鐨勫�?
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

//鍚姩 aardio-rpc 鏈嶅姟绔?externalServer.start();

winform.button.disabled = true;
winform.button.oncommand = function(id,event){
    externalServer.publish("testJs",1,2,3);
}

import nodeJs;

var js  =/*
var aardio = require('aardio')
aardio.test(123).then( v=>{ console.log(v) } );

aardio.on("testJs",function(...values){
    console.log("Node.js 鍑芥暟 testJs 琚皟鐢?,...values)
})

//鐢?aardio 瑙ｆ瀽妯℃澘瀛楃涓?const $ = aardio.tag;
$`abc${123}ddd${456}`.then( v=> console.log("妯℃澘瀛楃涓?",v)  )
*/

//鑷姩瀹夎 JS 浠ｇ爜涓紩鐢ㄧ殑妯″潡锛屽鏋滃凡缁忓畨瑁呬簡妯″潡锛岃繖鍙ヤ唬鐮佷細鑷姩蹇界暐涓嶆墽琛?nodeJs.prequireByJs(winform.edit,js);

//杩愯 Node.js 浠ｇ爜锛屽鏋滄敼鐢?nodeJs.startRpc() 鍒?JS 閲?console.log 涓嶅彲鐢?var node = nodeJs.exec(js);

//绐椾綋閫�鍑烘椂缁撴潫 nodeJs 杩涚▼
winform.onDestroy = function(){
    node.ctrlEvent(0)
}

//灏?Node.js 杩涚▼杈撳嚭鏄剧ず鍒版枃鏈锛屼笉浼氶樆濉炶繘绋?node.logResponse(winform.edit);

win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/nodeJs/external.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/nodeJs/external.md')

