[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: JSON 鎵╁睍

```aardio aardio
//JSON 鎵╁睍
import console;
import web.script.json;
var vm = web.script("VBScript");

vm.external = {
    log = function(...){
        console.log(...);
    };
}

vm.script = /*
Function TestFunction()

    '璋冪敤 aardio 鍏煎JSON锛孞SONP锛孞SON5锛岄儴鍒嗙被 YAML 璇硶鐨?web.json.parse() 鍑芥暟
    Set jObject = JSON.parse("{name:{a:123:b:456,c:[1,2,3]}}" )
    jObject.newKey = "娴嬭瘯"

    arr = jObject.name.c
    arr(0) = "娴嬭瘯"

    '閬嶅巻 JSON 鏁扮粍
    For Each item In arr
         external.log item
    Next

    TestFunction =  arr(0)
End Function
*/

//閫氳繃 vm.script.鍑芥暟鍚?) 璋冪敤 VBScript 鍑芥暟銆?var ret = vm.script.TestFunction();
console.dump(ret);
console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/VBScript/json.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/VBScript/json.md')

