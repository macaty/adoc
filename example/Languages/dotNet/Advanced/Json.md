[aardio 鏂囨。](../../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 璋冪敤 .NET 涔?JSON 杞崲

```aardio aardio
//aardio 璋冪敤 .NET 涔?JSON 杞崲
import console;
import web.json;
import dotNet.json;
import System.Collections;

//鍒涘缓 .NET 鐨?ArrayList 鏁扮粍
var arrList = System.Collections.ArrayList();

arrList.Add(123);
arrList.Add("瀛楃涓?);

//.NET 瀵硅薄杞崲涓?JSON
var json = dotNet.json.SerializeObject(arrList);
console.log(json);

//瀵煎叆 dotNet.json 浠ュ悗 web.json 浼氳嚜鍔ㄦ敮鎸?.NET瀵硅薄
console.log(web.json.stringify(arrList));

//杩欎釜鍑芥暟鍐呴儴涔熸槸璋冪敤 web.json.stringify
console.dumpJson(arrList);

//JSON 瑙ｆ瀽涓?.NET 瀵硅薄
var obj = dotNet.json.DeserializeObject(json);
console.log(obj);

/*------------------------------------------------------
 *浠ヤ笅涓鸿皟鐢?Newtonsoft.Json 瀹炵幇 JSON Path 鏌ヨ婕旂ず
------------------------------------------------------*/

JObject = dotNet.json.Linq.JObject;

//鍙傝�? https://www.newtonsoft.com/json/help/html/QueryJsonSelectToken.htm
var jObj = JObject.Parse("{
  'Space Invaders': ['Taito'],
  'Doom ]|[': 'id',
  ""Yar's Revenge"": 'Atari',
  'Government ""Intelligence""': 'Make-Believe'
}");

//JSON Path 鏌ヨ
var spaceInvaders = jObj.SelectToken("['Space Invaders']");

//.NET 瀵硅薄杞崲涓哄瓧绗︿覆
var str = tostring(spaceInvaders);
console.log(str);

//.NET 瀵硅薄杞崲涓虹函 aardio 瀵硅薄
var obj = web.json.strip(spaceInvaders);
console.dump(obj);

console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/Advanced/Json.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/Advanced/Json.md')

