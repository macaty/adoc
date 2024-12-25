[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: HTMLayout behavior用法演示

```aardio aardio
//自定�?behavior
import win.ui;
/*DSG{{*/
winform = win.form(text="HTMLayout behavior用法演示";right=599;bottom=399;)
winform.add()
/*}}*/

import web.sciter;
var sciter = web.sciter(winform);

//�?web.sciter.behavior 名字空间添加自定�?behavior
namespace web.sciter.behavior.sysdnd {

    onExchangeAcceptDrop = function( ltTarget,ltOwner,x,y,mode,scValueObject,exParams ) {
        return true; // 返回true表示接受系统拖放
    }

    onExchangeDrag =  function( ltTarget,ltOwner,x,y,mode,scValueObject,exParams ) {
        return true; // 拖而未放时触发，返回true表示支持继续拖放操作
    }

    onExchangeDrop =  function( ltTarget,ltOwner,x,y,mode,scValueObject,exParams ) {
        // scValueObject 参数�?web.sciter.valueObject 对象
        if(mode&2/*_SC_DD_MODE_MOVE*/){
            ltOwner.innerText = tostring(scValueObject)
            return true; // 返回true表示支持系统拖放
        }
    }

}

sciter.html =/***
<div class="sysdnd" 属�?"�?>请将外部文件等内容拖放到这里</div>
***/

sciter.css = /**
.sysdnd{
    behavior:sysdnd;
    height:100%%;
}
**/

winform.show()
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/WebUI/Sciter.JS/exchange.md)

