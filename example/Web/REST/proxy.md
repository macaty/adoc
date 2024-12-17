[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鐢?web.rest 瀹㈡埛绔皟鐢?HTTP API - 璁剧疆浠ｇ悊鏈嶅姟鍣?
```aardio aardio
//鐢?web.rest 瀹㈡埛绔皟鐢?HTTP API - 璁剧疆浠ｇ悊鏈嶅姟鍣?import console;
import inet.ipdata;
import web.rest.jsonClient;

//绗簩涓瀯閫犲弬鏁版寚瀹氫唬鐞嗘湇鍔″櫒
//浠ｇ悊閰嶇疆鏍煎紡: https://www.aardio.com/zh-cn/doc/library-guide/std/inet/proxy.html
var http = web.rest.jsonClient(,"socks=127.0.0.1:1081");

//澹版槑 HTTP 鎺ュ彛瀵硅薄
//澹版槑 API锛屽弬鏁?@3 鎸囧畾鐨勬ā寮忎覆鐢ㄤ簬鍖归厤杩斿洖鏁版嵁
var api = http.api("http://myip.ipip.net",,"(\d+\.\d+\.\d+\.\d+)");

//鍙戦�?GET 璇锋眰
var ip = api.get();

//鏄剧ず IP 鎵�鍦ㄥ湴
console.log( inet.ipdata().query(ip) )
console.pause(true);

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Web/REST/proxy.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Web/REST/proxy.md')

