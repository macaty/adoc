[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: Hello World / PHP\_CGI 服务�?
```aardio aardio
//aardio 调用 PHP - CGI
import win.ui;
/*DSG{{*/
var winform = win.form(text="Hello World / PHP_CGI 服务�?;right=759;bottom=469)
winform.add()
/*}}*/

import web.form;
var wb = web.form( winform);

/*
PHP 快速入�?https://quickref.me/zh-CN/docs/php.html
https://learnxinyminutes.com/docs/zh-cn/php-cn/
*/

//导入 php 扩展�?import process.php;

//生成测试 PHP 文件�?process.php.code["/test-cgi.php"] = /********
<html>
<head>
    <meta charset="utf-8">
    <title>PHP 测试</title>
</head>
<body>
    <?php echo '<p>Hello World / PHP_CGI 服务�?/p>'; ?>
</body>
********/

/*
启动多线�?HTTP 服务端，返回参数（可指定资源路径）指定页面的网址�?默认自动分配空闲端口。在同一线程可多次调用不会重复启�?HTTP 服务端�?当前线程结束 HTTP 服务端会自动退出�?*/
var url = process.php("/test-cgi.php");

wb.go(url);//调用浏览器组件显示网�?
winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/PHP/cgi.md)

