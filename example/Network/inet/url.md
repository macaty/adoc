[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: URL 解析

```aardio aardio
//URL 解析
import inet.url;
import inet.urlpart;
import console;

var str = "
需要传递特殊字符的场合,我们只要先将欲传递的内容先以UrlEncode 加以编码,
就可以保证所传递过去的值可以顺利被读到,而UrlDecode 方法则是将编码过的内容译�?..
"

var str = inet.url.encode(str);
console.log("Url Encode 编码" )
console.log( str );

str  = inet.url.decode(str)
console.log("Url Encode 解码" )
console.log( str );

url = "http://www.aardio.com/bbs/showtopic-7374.aspx#name?username=用户�?

turl = inet.url.split(url );
console.log( "inet.url.split()函数 拆分URL" )
console.log( "协议",turl.scheme )
console.log( "主机",turl.host )
console.log( "路径",turl.path )
console.log( "参数",turl.extraInfo )
console.log( "完整URL",tostring(turl) )

console.log()
console.log( "url参数(不带问号)",inet.urlpart.getQuery(url) )

console.log()
console.log("计算哈希�?,inet.url.hashNum(url))

console.log()
console.log("转换URL相对路径",inet.url.joinpath(url,"../test.aspx"))

console.log()
console.log( "mailto:web@aardio.com是OPAQUE URL�?
    ,inet.url.is("mailto:web@aardio.com"
        ,0x1/*_URLIS_OPAQUE*/)
)

console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Network/inet/url.md)

