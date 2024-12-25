[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: �?web.rest 客户端调�?HTTP API - 设置 HTTP �?
```aardio aardio
//�?web.rest 客户端调�?HTTP API - 设置 HTTP �?
import crypt;
import web.rest.jsonLiteClient;

var http = web.rest.jsonLiteClient();

//设置默认添加到所有请求的 HTTP �?http.addHeaders = { ["X-Auth-Token"] = "自定�?Token" }

//如果 addHeaders 是表则添加所有请求都要添加的 HTTP 头，否则替换请求头�?http.setHeaders(
    ["Test"] = "test"
)

//使用默认�?Authorization 请求头指�?token
http.setAuthToken("token");

/*
如果每次请求都要修改HTTP头，可以写到这个事件�?
*/
http.beforeRequestHeaders = function(params){
    var apiKey = "";
    var secretKey = "";
    var authorization = {
        ["apiKey"] = apiKey;
        ["time"] = tonumber(time());
    }

    authorization["sign"] = crypt.md5(apiKey ++ secretKey ++ authorization.time)

    //通过返回值设置本次请求的HTTP�? Content-Type不需要指定（会自动指定）
    return {
        ["Authorization"] = crypt.encodeBin(web.json.stringify(authorization))
    };
}

var api = http.api("http://httpbin.org/anything");

var jsonData = api.post({
    用户�?= "用户�?;
    密码 = "密码";
})

import console;
console.dumpJson(jsonData)
console.pause(true);

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Web/REST/headers.md)

