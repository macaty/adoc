[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鐢?web.rest 瀹㈡埛绔皟鐢?HTTP API - 鑷姩妯″紡鍖归厤

```aardio aardio
//鐢?web.rest 瀹㈡埛绔皟鐢?HTTP API - 鑷姩妯″紡鍖归厤
import console;
console.showLoading("鑾峰彇澶栫綉IP");

import web.rest.client;
var http = web.rest.client();

//澹版槑 API锛屽弬鏁?@3 鎸囧畾鐨勬ā寮忎覆鐢ㄤ簬鍖归厤杩斿洖鏁版嵁
var api = http.api("http://myip.ipip.net",,"(\d+\.\d+\.\d+\.\d+)");

//璋冪敤 HTTP 鎺ュ彛
var ip = api.get();

//鏄剧ず鏌ヨ缁撴灉
console.log( ip  );

console.pause(true);

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Web/REST/match.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Web/REST/match.md')

