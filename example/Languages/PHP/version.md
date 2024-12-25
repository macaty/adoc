[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 PHP - 切换版本

```aardio aardio
//aardio 调用 PHP - 切换版本
import console;

//自动搜索适合�?PHP 版本，找不到�?Win7 自动下载 PHP 7.x，Win10 自动下载 PHP 8.x
//import process.php;

//PHP 5.2，略慢，支持 XP 系统。调�?process.php 扩展库自带的 PHP 环境�?//import process.php.5.2;

//PHP 7.4，速度快，没安装会自动下载，支�?Win7 以及之后的系统�?//import process.php.7.4;

//PHP 8.3，速度快，没安装会自动下载，支�?Win10 以及之后的系统�?//import process.php.8.3;

//使用时应去掉扩展库版本号，例如：
/*
import process.php.7.4;
console.log( process.php.checkCgiPath() );
*/

console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/PHP/version.md)

