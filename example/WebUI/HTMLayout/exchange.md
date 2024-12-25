[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: HTMLayout系统拖放演示

```aardio aardio
//系统拖放
import win.ui;
/*DSG{{*/
var winform = win.form(text="HTMLayout系统拖放演示";right=599;bottom=399)
winform.add()
/*}}*/

import web.layout;
var wbLayout = web.layout(winform,0xFFFF/*_HL_HANDLE_ALL*/);

namespace web.layout.behavior.sysdnd{

    onExchangeDrag = function( ltTarget,ltOwner,x,y,cmd,dataTypes,fetchData,exParams ) {
        return true;//返回true表示支持系统拖放
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
<div id="destination" style="behavior:sysdnd;height:100%%;">拖动一个或多个外部文件到这�?/div>
**/

winform.show()
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/WebUI/HTMLayout/exchange.md)

