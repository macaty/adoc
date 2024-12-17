[aardio 鏂囨。](../../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 浣跨敤妯℃澘璇硶缂栬瘧骞惰繍琛?C\# 浠ｇ爜

```aardio aardio
//aardio 浣跨敤妯℃澘璇硶缂栬瘧骞惰繍琛?C# 浠ｇ爜
//dotNet.desktop 鎵╁睍搴撲娇鐢ㄤ簡杩欑鎶�鏈?import win.version;
import dotNet;
var compiler = dotNet.createCompiler("C#");

//鏀寔妯℃澘璇硶锛?https://www.aardio.com/zh-cn/doc/language-reference/templating/syntax.html
compiler.Source = /***
?> //C#婧愮爜濡傛灉璧峰浜庢湰琛屽墠闈㈢殑 aardio 妯℃澘鏍囪鍒欐敮鎸佹ā鏉胯娉?namespace CSharpLibrary
{
    public class Object
    {
        <? if _WINXP { ?>
        public string Test(){
            return "Windows XP";
        }
        <? } else { ?>
        public string Test(){
            return "<?= win.version.name ?>";
        }
        <? } ?>
    }
}
***/

//缂栬瘧鍐呭瓨绋嬪簭闆嗭紝瀵煎叆鍚嶅瓧绌洪棿
compiler.import("CSharpLibrary");

//浣跨敤 C# 缂栧啓鐨勭被鏋勯�犲璞″疄渚?var netObj = CSharpLibrary.Object();

//璋冪敤瀹炴椂缂栬瘧鐨凜#鍑芥暟
var ret = netObj.Test();

import console;
console.log( ret );
console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/Advanced/template-compiler.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/Advanced/template-compiler.md')

