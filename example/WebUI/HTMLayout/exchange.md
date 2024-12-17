[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: HTMLayout绯荤粺鎷栨斁婕旂ず

```aardio aardio
//绯荤粺鎷栨斁
import win.ui;
/*DSG{{*/
var winform = win.form(text="HTMLayout绯荤粺鎷栨斁婕旂ず";right=599;bottom=399)
winform.add()
/*}}*/

import web.layout;
var wbLayout = web.layout(winform,0xFFFF/*_HL_HANDLE_ALL*/);

namespace web.layout.behavior.sysdnd{

    onExchangeDrag = function( ltTarget,ltOwner,x,y,cmd,dataTypes,fetchData,exParams ) {
        return true;//杩斿洖true琛ㄧず鏀寔绯荤粺鎷栨斁
    }

    onExchangeDrop = function( ltTarget,ltOwner,x,y,cmd,dataTypes,fetchData,exParams ) {
        var data,dataType = fetchData( 0x10/*_HL_EXF_FILE*/ );
        if( data ) {
            wbLayout.getEle("destination").innerHTML = ..string.join(data,"<br>")
            return true;
        }
    }
}

wbLayout.html = /**
<div id="destination" style="behavior:sysdnd;height:100%%;">鎷栧姩涓�涓垨澶氫釜澶栭儴鏂囦欢鍒拌繖閲?/div>
**/

winform.show()
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/WebUI/HTMLayout/exchange.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/WebUI/HTMLayout/exchange.md')

