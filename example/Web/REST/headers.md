[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鐢?web.rest 瀹㈡埛绔皟鐢?HTTP API - 璁剧疆 HTTP 澶?
```aardio aardio
//鐢?web.rest 瀹㈡埛绔皟鐢?HTTP API - 璁剧疆 HTTP 澶?
import crypt;
import web.rest.jsonLiteClient;

var http = web.rest.jsonLiteClient();

//璁剧疆榛樿娣诲姞鍒版墍鏈夎姹傜殑 HTTP 澶?http.addHeaders = { ["X-Auth-Token"] = "鑷畾涔?Token" }

//濡傛灉 addHeaders 鏄〃鍒欐坊鍔犳墍鏈夎姹傞兘瑕佹坊鍔犵殑 HTTP 澶达紝鍚﹀垯鏇挎崲璇锋眰澶淬�?http.setHeaders(
    ["Test"] = "test"
)

//浣跨敤榛樿鐨?Authorization 璇锋眰澶存寚瀹?token
http.setAuthToken("token");

/*
濡傛灉姣忔璇锋眰閮借淇敼HTTP澶达紝鍙互鍐欏埌杩欎釜浜嬩欢閲?
*/
http.beforeRequestHeaders = function(params){
    var apiKey = "";
    var secretKey = "";
    var authorization = {
        ["apiKey"] = apiKey;
        ["time"] = tonumber(time());
    }

    authorization["sign"] = crypt.md5(apiKey ++ secretKey ++ authorization.time)

    //閫氳繃杩斿洖鍊艰缃湰娆¤姹傜殑HTTP澶? Content-Type涓嶉渶瑕佹寚瀹氾紙浼氳嚜鍔ㄦ寚瀹氾級
    return {
        ["Authorization"] = crypt.encodeBin(web.json.stringify(authorization))
    };
}

var api = http.api("http://httpbin.org/anything");

var jsonData = api.post({
    鐢ㄦ埛鍚?= "鐢ㄦ埛鍚?;
    瀵嗙爜 = "瀵嗙爜";
})

import console;
console.dumpJson(jsonData)
console.pause(true);

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Web/REST/headers.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Web/REST/headers.md')

