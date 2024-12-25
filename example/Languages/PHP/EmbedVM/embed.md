[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 嵌入式调 PHP

```aardio aardio
//aardio 嵌入式调 PHP
import php;
import console;

/*
嵌入�?PHP 解释器的版本�?5.2.17�?如果希望支持高版�?PHP，应当使�?process.php 通过 CGI 方式调用 PHP,
高版�?PHP 体积较大、需要单独安装，不适合绿色打包，但要注�?PHP 5.2 默认编码�?GBK，�?aardio �?UTF-8 编码
*/

//PHP代码
var phpcode =/*
    $a="我是PHP中的变量a";
    function main(){
        global $a;
        return $a." 这是main()函数的返回�?;
    };
*/

//运行PHP代码
php.exec(phpcode)

//运行 PHP 代码,调用函数返回�?不要使用 eval 执行太长的代�?eval 不能捕获PHP中的致命错误
var ret = php.eval("main()")
console.log( ret );

//运行 PHP 代码,返回表达式的�?var ret = php.eval("8899")
console.log( ret );

//再用 eval 函数访问 PHP 中的变量
var ret = php.eval("$a")
console.log( ret );

//更简单一�?直接读PHP中的变量，注意去掉变量前面的$符号
console.log("直接读取PHP中的变量", php.a )

//同上,也可以直接修改PHP中的变量
php.global_abc = 2011

//请注�? PHP返回给aardio的值都是字符串类型
console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/PHP/EmbedVM/embed.md)

