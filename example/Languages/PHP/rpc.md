[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 璋冪敤 PHP 鍑芥暟

```aardio aardio
//aardio 璋冪敤 PHP 鍑芥暟
import console.int;
import process.php;

var phpCode = /*
function add($a,$b) {
    return $a + $b;
}

class Calculator {
    public function add($a, $b) {
        return $a + $b;
    }
}

$calculator = new Calculator();
*/

//鍚姩 PHP 鏈嶅姟绔紝鍏煎浠绘剰鐗堟湰 PHP
var php = process.php.startRpc(phpCode); //鍙傛暟鍙互鏄?PHP 浠ｇ爜锛屼篃鍙互鏄?PHP 鏂囦欢璺緞

//璋冪敤 PHP 鍑芥暟
var ret,err = php.add(2,3);

//鑾峰彇杩斿洖鍊?ret = ret[["result"]];

//璋冪敤 PHP 瀵硅薄鐨勬垚鍛樺嚱鏁帮紙RPC 璋冪敤浼氶噸鐢ㄥ悓涓� PHP 杩涚▼锛屽娆¤皟鐢ㄦ瘮鏅�?CGI 鏇村揩锛?var ret,err = php.calculator.add(2,3);

//鑾峰彇杩斿洖鍊?ret = ret[["result"]];
console.dump(ret);

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/PHP/rpc.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/PHP/rpc.md')

