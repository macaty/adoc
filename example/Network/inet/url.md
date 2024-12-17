[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: URL 瑙ｆ瀽

```aardio aardio
//URL 瑙ｆ瀽
import inet.url;
import inet.urlpart;
import console;

var str = "
闇�瑕佷紶閫掔壒娈婂瓧绗︾殑鍦哄悎,鎴戜滑鍙鍏堝皢娆蹭紶閫掔殑鍐呭鍏堜互UrlEncode 鍔犱互缂栫爜,
灏卞彲浠ヤ繚璇佹墍浼犻�掕繃鍘荤殑鍊煎彲浠ラ『鍒╄璇诲埌,鑰孶rlDecode 鏂规硶鍒欐槸灏嗙紪鐮佽繃鐨勫唴瀹硅瘧鐮?..
"

var str = inet.url.encode(str);
console.log("Url Encode 缂栫爜" )
console.log( str );

str  = inet.url.decode(str)
console.log("Url Encode 瑙ｇ爜" )
console.log( str );

url = "http://www.aardio.com/bbs/showtopic-7374.aspx#name?username=鐢ㄦ埛鍚?

turl = inet.url.split(url );
console.log( "inet.url.split()鍑芥暟 鎷嗗垎URL" )
console.log( "鍗忚",turl.scheme )
console.log( "涓绘満",turl.host )
console.log( "璺緞",turl.path )
console.log( "鍙傛暟",turl.extraInfo )
console.log( "瀹屾暣URL",tostring(turl) )

console.log()
console.log( "url鍙傛暟(涓嶅甫闂彿)",inet.urlpart.getQuery(url) )

console.log()
console.log("璁＄畻鍝堝笇鍊?,inet.url.hashNum(url))

console.log()
console.log("杞崲URL鐩稿璺緞",inet.url.joinpath(url,"../test.aspx"))

console.log()
console.log( "mailto:web@aardio.com鏄疧PAQUE URL鍚?
    ,inet.url.is("mailto:web@aardio.com"
        ,0x1/*_URLIS_OPAQUE*/)
)

console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Network/inet/url.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 服务器报告访问的文件是隐藏的。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Network/inet/url.md')

