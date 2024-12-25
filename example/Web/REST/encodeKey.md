[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: �?web.rest 客户端调�?HTTP API - 资源名编�?
```aardio aardio
//�?web.rest 客户端调�?HTTP API - 资源名编�?import console;
import web.rest.jsonLiteClient;
import crypt.bin;

var http = web.rest.jsonLiteClient();

//自定义资源名内中文字符改�?Base64 编码
http.encodeKey = lambda(v) string.replace(v,":",crypt.bin.encodeUrlBase64);

//创建 API
var countApi = http.api("https://api.countapi.xyz/hit{/domain}{/key}")

//调用 API
var data = countApi["example.com"]["password"].get();
console.log( data[["value"]] );

//这样写也可以
var data = countApi[{
    domain = "example.com";
    key = "password"
}].get();

//省略一个参数也可以
var data = countApi["测试一�?aardio范例"].get();
console.log( data[["value"]] );

console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Web/REST/encodeKey.md)

