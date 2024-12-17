[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: HTMLayout behavior鐢ㄦ硶婕旂ず

```aardio aardio
//鑷畾涔?behavior
import win.ui;
/*DSG{{*/
winform = win.form(text="HTMLayout behavior鐢ㄦ硶婕旂ず";right=599;bottom=399;)
winform.add()
/*}}*/

import web.sciter;
var sciter = web.sciter(winform);

//鍦?web.sciter.behavior 鍚嶅瓧绌洪棿娣诲姞鑷畾涔?behavior
namespace web.sciter.behavior.sysdnd {

    onExchangeAcceptDrop = function( ltTarget,ltOwner,x,y,mode,scValueObject,exParams ) {
        return true; // 杩斿洖true琛ㄧず鎺ュ彈绯荤粺鎷栨斁
    }

    onExchangeDrag =  function( ltTarget,ltOwner,x,y,mode,scValueObject,exParams ) {
        return true; // 鎷栬�屾湭鏀炬椂瑙﹀彂锛岃繑鍥瀟rue琛ㄧず鏀寔缁х画鎷栨斁鎿嶄綔
    }

    onExchangeDrop =  function( ltTarget,ltOwner,x,y,mode,scValueObject,exParams ) {
        // scValueObject 鍙傛暟鏄?web.sciter.valueObject 瀵硅薄
        if(mode&2/*_SC_DD_MODE_MOVE*/){
            ltOwner.innerText = tostring(scValueObject)
            return true; // 杩斿洖true琛ㄧず鏀寔绯荤粺鎷栨斁
        }
    }

}

sciter.html =/***
<div class="sysdnd" 灞炴�?"鍊?>璇峰皢澶栭儴鏂囦欢绛夊唴瀹规嫋鏀惧埌杩欓噷</div>
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

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/WebUI/Sciter.JS/exchange.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/WebUI/Sciter.JS/exchange.md')

