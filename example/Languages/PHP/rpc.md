[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 PHP 函数

```aardio aardio
//aardio 调用 PHP 函数
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

//启动 PHP 服务端，兼容任意版本 PHP
var php = process.php.startRpc(phpCode); //参数可以�?PHP 代码，也可以�?PHP 文件路径

//调用 PHP 函数
var ret,err = php.add(2,3);

//获取返回�?ret = ret[["result"]];

//调用 PHP 对象的成员函数（RPC 调用会重用同一 PHP 进程，多次调用比普�?CGI 更快�?var ret,err = php.calculator.add(2,3);

//获取返回�?ret = ret[["result"]];
console.dump(ret);

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/PHP/rpc.md)

