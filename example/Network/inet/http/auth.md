[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 认证登录

```aardio aardio
//认证登录
import console;
import inet.http;

var http = inet.http();

//设置登录用户名与密码
http.username = "user";
http.password = "passwd"

//Digest 认证
var info = http.get( "http://httpbin.org/digest-auth/auth/user/passwd" );
console.dump(info);

//Basic 认证
var info = http.get( "http://httpbin.org/basic-auth/user/passwd" );
console.dump(info);

import web.rest.jsonLiteClient;
var http = web.rest.jsonLiteClient();
var auth = http.api("http://httpbin.org/digest-auth/auth/");

//设置登录用户名与密码
http.setAuth("user","passwd");

//发送请�?console.dumpJson( auth["user"]["passwd"].get() )

console.pause(true);

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Network/inet/http/auth.md)

