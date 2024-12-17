[aardio 鏂囨。](../../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 璁よ瘉鐧诲綍

```aardio aardio
//璁よ瘉鐧诲綍
import console;
import inet.http;

var http = inet.http();

//璁剧疆鐧诲綍鐢ㄦ埛鍚嶄笌瀵嗙爜
http.username = "user";
http.password = "passwd"

//Digest 璁よ瘉
var info = http.get( "http://httpbin.org/digest-auth/auth/user/passwd" );
console.dump(info);

//Basic 璁よ瘉
var info = http.get( "http://httpbin.org/basic-auth/user/passwd" );
console.dump(info);

import web.rest.jsonLiteClient;
var http = web.rest.jsonLiteClient();
var auth = http.api("http://httpbin.org/digest-auth/auth/");

//璁剧疆鐧诲綍鐢ㄦ埛鍚嶄笌瀵嗙爜
http.setAuth("user","passwd");

//鍙戦�佽姹?console.dumpJson( auth["user"]["passwd"].get() )

console.pause(true);

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Network/inet/http/auth.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 服务器报告访问的文件是隐藏的。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Network/inet/http/auth.md')

