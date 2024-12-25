[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: �?web.rest 客户端调�?HTTP API - 登录认证

```aardio aardio
//�?web.rest 客户端调�?HTTP API - 登录认证
import console;
import web.rest.jsonClient;
console.showLoading("正在登录")

//创建 HTTP 客户�?var http = web.rest.jsonClient();

/*
使用默认�?Authorization 请求头指定认�?token�?调用 http.setAuth 会清�?http.setAuthToken 的设置，
调用 http.setAuthToken  也会清除 http.setAuth 的设置�?*/
http.setAuthToken("token");

//设置登录信息，支�?Basic , Digest 认证
http.setAuth("user","passwd");

var api = http.api( "http://httpbin.org" );

//发�?GET 请求
var info = api["digest-auth"].auth["user"]["passwd"].get();
//var info = http.get( "http://httpbin.org/digest-auth/auth/user/passwd" );
console.dumpJson(info);

console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Web/REST/auth.md)

