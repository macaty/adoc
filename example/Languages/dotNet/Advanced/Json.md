[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 .NET �?JSON 转换

```aardio aardio
//aardio 调用 .NET �?JSON 转换
import console;
import web.json;
import dotNet.json;
import System.Collections;

//创建 .NET �?ArrayList 数组
var arrList = System.Collections.ArrayList();

arrList.Add(123);
arrList.Add("字符�?);

//.NET 对象转换�?JSON
var json = dotNet.json.SerializeObject(arrList);
console.log(json);

//导入 dotNet.json 以后 web.json 会自动支�?.NET对象
console.log(web.json.stringify(arrList));

//这个函数内部也是调用 web.json.stringify
console.dumpJson(arrList);

//JSON 解析�?.NET 对象
var obj = dotNet.json.DeserializeObject(json);
console.log(obj);

/*------------------------------------------------------
 *以下为调�?Newtonsoft.Json 实现 JSON Path 查询演示
------------------------------------------------------*/

JObject = dotNet.json.Linq.JObject;

//参�? https://www.newtonsoft.com/json/help/html/QueryJsonSelectToken.htm
var jObj = JObject.Parse("{
  'Space Invaders': ['Taito'],
  'Doom ]|[': 'id',
  ""Yar's Revenge"": 'Atari',
  'Government ""Intelligence""': 'Make-Believe'
}");

//JSON Path 查询
var spaceInvaders = jObj.SelectToken("['Space Invaders']");

//.NET 对象转换为字符串
var str = tostring(spaceInvaders);
console.log(str);

//.NET 对象转换为纯 aardio 对象
var obj = web.json.strip(spaceInvaders);
console.dump(obj);

console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/Advanced/Json.md)

