[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鐢?web.rest 瀹㈡埛绔皟鐢?HTTP API - 鐧诲綍璁よ瘉

```aardio aardio
//鐢?web.rest 瀹㈡埛绔皟鐢?HTTP API - 鐧诲綍璁よ瘉
import console;
import web.rest.jsonClient;
console.showLoading("姝ｅ湪鐧诲綍")

//鍒涘缓 HTTP 瀹㈡埛绔?var http = web.rest.jsonClient();

/*
浣跨敤榛樿鐨?Authorization 璇锋眰澶存寚瀹氳璇?token銆?璋冪敤 http.setAuth 浼氭竻闄?http.setAuthToken 鐨勮缃紝
璋冪敤 http.setAuthToken  涔熶細娓呴櫎 http.setAuth 鐨勮缃�?*/
http.setAuthToken("token");

//璁剧疆鐧诲綍淇℃伅锛屾敮鎸?Basic , Digest 璁よ瘉
http.setAuth("user","passwd");

var api = http.api( "http://httpbin.org" );

//鍙戦�?GET 璇锋眰
var info = api["digest-auth"].auth["user"]["passwd"].get();
//var info = http.get( "http://httpbin.org/digest-auth/auth/user/passwd" );
console.dumpJson(info);

console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Web/REST/auth.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Web/REST/auth.md')

