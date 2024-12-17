[aardio 鏂囨。](../../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 瑙ｆ瀽 PHP 鏂囦欢

```aardio aardio
//aardio 瑙ｆ瀽 PHP 鏂囦欢
import web.form;
/*DSG{{*/
var winform = win.form(text="aardio form";right=713;bottom=652;scroll=1)
winform.add()
/*}}*/

//鍒涘缓web绐椾綋
var wb = web.form( winform  );
wb.go("about:blank")

import php;
php.print = function( msg ) {
    wb.document.write(msg)
}

//鐢熸祴娴嬭瘯鐨凱HP鏂囦欢
phpcode = /*
<?php
    echo "<p>Hello World</p>";
    phpinfo(INFO_ALL);
?>
*/

string.save("/test.php",phpcode )
php.dofile("/test.php")

//鐩存帴鍐?php.exec( phpcode ) 涔熷彲浠?php.exec( phpcode )

//鏄剧ず绐椾綋
winform.show()
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/PHP/EmbedVM/embed.dofile.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/PHP/EmbedVM/embed.dofile.md')

