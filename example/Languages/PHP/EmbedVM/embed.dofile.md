[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 解析 PHP 文件

```aardio aardio
//aardio 解析 PHP 文件
import web.form;
/*DSG{{*/
var winform = win.form(text="aardio form";right=713;bottom=652;scroll=1)
winform.add()
/*}}*/

//创建web窗体
var wb = web.form( winform  );
wb.go("about:blank")

import php;
php.print = function( msg ) {
    wb.document.write(msg)
}

//生测测试的PHP文件
phpcode = /*
<?php
    echo "<p>Hello World</p>";
    phpinfo(INFO_ALL);
?>
*/

string.save("/test.php",phpcode )
php.dofile("/test.php")

//直接�?php.exec( phpcode ) 也可�?php.exec( phpcode )

//显示窗体
winform.show()
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/PHP/EmbedVM/embed.dofile.md)

