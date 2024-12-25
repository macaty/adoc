[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: PHP 调用 aardio

```aardio aardio
//PHP 调用 aardio
import php;
import console;

//PHP代码
var phpCode =/*
    $ret = aardio("
        import win;
        import web.json;

        win.msgbox('我是 aardio 代码');
        return web.json.stringify({a=123;b=456});
    ")
*/

//运行PHP代码,返回表达式的�?var ret = php.eval(phpCode)
console.log( ret );

console.pause();

//================================
//请注�? aardio 返回给PHP的值都是字符串类型
//aardio 代码使用 return 语句返回值�?
```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/PHP/EmbedVM/embedaardio.md)

