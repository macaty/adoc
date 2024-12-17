[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鐢?web.rest 瀹㈡埛绔皟鐢?HTTP API - 璧勬簮鍚嶇紪鐮?
```aardio aardio
//鐢?web.rest 瀹㈡埛绔皟鐢?HTTP API - 璧勬簮鍚嶇紪鐮?import console;
import web.rest.jsonLiteClient;
import crypt.bin;

var http = web.rest.jsonLiteClient();

//鑷畾涔夎祫婧愬悕鍐呬腑鏂囧瓧绗︽敼涓?Base64 缂栫爜
http.encodeKey = lambda(v) string.replace(v,":",crypt.bin.encodeUrlBase64);

//鍒涘缓 API
var countApi = http.api("https://api.countapi.xyz/hit{/domain}{/key}")

//璋冪敤 API
var data = countApi["example.com"]["password"].get();
console.log( data[["value"]] );

//杩欐牱鍐欎篃鍙互
var data = countApi[{
    domain = "example.com";
    key = "password"
}].get();

//鐪佺暐涓�涓弬鏁颁篃鍙互
var data = countApi["娴嬭瘯涓�涓?aardio鑼冧緥"].get();
console.log( data[["value"]] );

console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Web/REST/encodeKey.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Web/REST/encodeKey.md')

