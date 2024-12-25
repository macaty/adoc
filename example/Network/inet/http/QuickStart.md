[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 入门

```aardio aardio
//入门
/*
inet.http �?inet.whttp 用法与接口基本相同，一般可相互替代�?普通桌面客户端软件(非NT服务)请使�?inet.http（WinINet�?而不应该使用 inet.whttp（WinHTTP）�?基于 inet.http 而封装的 web.rest.client 可能在很多应用中都是更好的选择�?
inet.http 入门教程�?https://mp.weixin.qq.com/s/3Xp4c1LxsOQJsux5o8bhvA
*/
import console;
console.showLoading(" 正在发送请�?);

import inet.http;

//创建 HTTP 客户端对�?var http = inet.http();

//发�?GET 请求
var data = http.get("http://eu.httpbin.org/get?username=user&password=pwd");

//发�?POST 请求
var data = http.post("http://eu.httpbin.org/post","username=user&password=pwd" );

//上面�?POST 请求参数也可以写为表参数
var data = http.post("http://eu.httpbin.org/post",{
    username = "user"; password = "pwd";
});

//显示服务器返回的网页 HTML
console.log(data);

//关闭对象。http 对象被回收时也会自动调用 http.close()，主动调用一下当然更�?http.close();

console.pause(true);

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Network/inet/http/QuickStart.md)

