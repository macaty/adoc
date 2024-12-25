[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 嵌入式调 PHP - 重置解释�?
```aardio aardio
//aardio 嵌入式调 PHP - 重置解释�?import php;
import console;

console.open();

php.begin()

    php.eval("$a=123");
    console.log( php.a );

php.end()

php.begin()

    php.eval("$b=456");
    console.log( php.a,php.b );//注意这里PHP中的变量$a已经失效

php.end()

console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/PHP/EmbedVM/embed.reset.md)

