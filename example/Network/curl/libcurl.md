[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 璋冪敤 API

```aardio aardio
//璋冪敤 API
import curl;
import console;

var http = curl.easy();//鍒涘缓瀹㈡埛绔?
//POST婕旂ず
console.showLoading("姝ｅ湪杩炴帴缃戦〉");
var str = http.post("http://httpbin.org/post"
        ,"username=jacen&password=123456");
console.log(str);

//鍙傛暟涔熷彲浠ユ寚瀹氫竴涓〃
var str = http.post("http://httpbin.org/post" ,{
    username = "jacen";
    password="123456";
});
console.log(str);

//GET婕旂ず
var str = http.get("http://www.aardio.com");
console.log(str);

/*
鏇村鐢ㄦ硶璇峰弬鑰冿細
https://bbs.aardio.com/forum.php?mod=viewthread&tid=9319

鏇存帹鑽愪娇鐢?web.rest 锛堜綋绉皬锛屽熀浜庣郴缁熻嚜甯︾粍浠讹紝鐢ㄦ硶鏇寸畝鍗曪級
https://mp.weixin.qq.com/s/4mYRDnO49alwpQoBD_cILg

鎴栦娇鐢?inet.http  锛堜綋绉皬锛屽熀浜庣郴缁熻嚜甯︾粍浠讹紝鐢ㄦ硶鏇寸畝鍗曪級
https://mp.weixin.qq.com/s/3Xp4c1LxsOQJsux5o8bhvA
*/

console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Network/curl/libcurl.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Network/curl/libcurl.md')

