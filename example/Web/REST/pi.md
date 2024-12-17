[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鐢?web.rest 瀹㈡埛绔皟鐢?HTTP API - 鑾峰彇鍦嗗懆鐜?
```aardio aardio
//鐢?web.rest 瀹㈡埛绔皟鐢?HTTP API - 鑾峰彇鍦嗗懆鐜?import console.int;
import web.rest.jsonLiteClient;

var http = web.rest.jsonLiteClient();

//鍙煡璇㈠墠 100 涓囦嚎浣嶇殑鍦嗗懆鐜囷紝涔熸槸鐩墠鏈�闀跨殑鍦ㄧ嚎鍙敤鍦嗗懆鐜囨暟鎹簱涔嬩竴
var delivery = http.api("https://api.pi.delivery/v1/pi");

//鏌ヨ鍦嗗懆鐜囷紝鍙傛暟鎸囧畾涓�涓〃瀵硅薄锛坱able锛夛紝鍗曚釜琛ㄥ弬鏁板灞傜殑 {} 鍙互鐪佺暐涓嶅啓
var ret = delivery.get(
    start=1, //浠庣 1 浣嶅紑濮?    numberOfDigits=100 //杩斿洖 100 浣嶅渾鍛ㄧ巼
)

//鏄剧ず鍦嗗懆鐜?console.log("3."+ ret.content)

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Web/REST/pi.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Web/REST/pi.md')

