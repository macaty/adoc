[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鍑芥暟鎵╁睍

```aardio aardio
//鍑芥暟鎵╁睍

import util;
import console;

//util.bind鍙敤浜庝慨鏀瑰嚱鏁扮殑榛樿瀹炲弬,骞剁敓鎴愭柊鐨勫嚱鏁?string.findMail = util.bind( string.match, ,"\w+[\w\-\.]+\w@\w+[\w\-]*\w\.[\w\-\.]*\w{2,}" )
string.endWith = util.bind( string.endWith, , ,true)

console.log(
    string.findMail("aaaaaaaaaa web@aardio.com "),
    string.endWith( "a abc","ABC" )
)

//===================================================
var func = function(){
    console.log("a")
}

var proc = function(){
    console.log("b")
}

//鍦ㄨ皟鐢ㄤ竴涓嚱鏁板墠瑙﹀彂閽╁瓙鍑芥暟,閽╁瓙鍑芥暟杩斿洖浠绘剰闈炵┖鍊煎彲涓鐩爣鍑芥暟鎵ц
var func = util.before(,func,proc);
func()

//===================================================
var tab = {
    name = "鍚嶅瓧";
    func = function(){
        console.log( owner[["name"]] )
    }
}

var func = tab.func;
func() //璋冪敤澶辫触

var func = util.hitch(tab,"func");
func() //owner瀵硅薄涓嶅啀鍙楀墠缂�褰卞搷

console.pause()

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/aardio/Util/func.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/aardio/Util/func.md')

