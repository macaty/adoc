[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 正则表达�? preg )

```aardio aardio
//正则表达�? preg )
import preg;
import console;

/*
preg 扩展库教�? http://bbs.aardio.com/forum.php?mod=viewthread&tid=8910
正则表达式速览: https://quickref.me/regex
*/
var regex = preg("(\w+\:\/\/)(?P<host>[\w.]+)");

var testString = /*
http://bbs.aardio.com
https://www.example.com
*/

console.log( "测试是否匹配", regex.test(testString) );
console.log( "查找匹配位置", regex.find(testString) );
console.log( "获取匹配字符�?, regex.match(testString) );

//全局匹配
for scheme,host in regex.gmatch( testString  ) {
    console.log("发现匹配字符�?, scheme,host )
}

console.log( '字符串替换结果\r\n', regex.replace( testString,"ftp://\2" ) );

console.log( '函数替换结果\r\n', regex.replace( testString
    ,function(scheme,host){
        if( host == "bbs.aardio.com" )
            return "ftp://" + host;
    }  ) );

//数组匹配,找出所有网址并返回数�?var urls = regex.grep( {
    "http://bbs.aardio.com";
    "www.aardio.net";
    "http://www.example.com";
} );

console.varDump(urls)
regex.free();

var $keywords = preg("/[\s,]/is").split ( "hypertext language,,programming");
console.varDump( $keywords )

console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Text/regex.md)

