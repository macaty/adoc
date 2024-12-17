[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: web.rest 瀹㈡埛绔?- web.rest.jsonClient

```aardio aardio
//web.rest 瀹㈡埛绔?- web.rest.jsonClient
import console;
import web.rest.jsonClient;

console.showLoading("姝ｅ湪杩炴帴JSON鏁版嵁搴?);
var http = web.rest.jsonClient();
http.setHeaders({
    ["Security-key"] =  "Your security key";
    ["Private"] = true;
})

var jsonStore = http.api("https://extendsclass.com/api/json-storage/bin/");
var jsonData = jsonStore.post(
    name = "jon.snow";
    age = 31;
)
console.log("澧烇紝浠?POST 鏂规硶璇锋眰缃戝潃",http.lastRequestUrl)

var result = jsonStore[jsonData.id].put(
    name = "jon.snow2";
    age = 32;
)
console.log("鏀癸紝浠?PUT 鏂规硶璇锋眰缃戝潃",http.lastRequestUrl)

var result = jsonStore[jsonData.id].patch(
    name = "jon.snow3";
)
console.log("閮ㄥ垎淇敼锛屼互 PATCH 鏂规硶璇锋眰缃戝潃",http.lastRequestUrl)

//涔熷彲浠ュ湪缃戝潃涓娇鐢ㄥぇ鎷彿鎸囧畾鍗犱綅绗?var jsonStore = http.api("https://extendsclass.com/api/json-storage/bin/{id}");

//API瀵硅薄鐨勬垚鍛樺悕浼氳鑷姩鎸夐『搴忔浛鎹负URL鍗犱綅绗︼紙蹇界暐鍗犱綅绗︾殑鍚嶅瓧锛?var result = jsonStore[jsonData.id].get();
console.log("鏌ワ紝浠?GET 鏂规硶璇锋眰缃戝潃",http.lastRequestUrl)
console.dumpJson(result)

//涔熷彲浠ョ敤涓�涓〃鎸囧畾澶氫釜鍗犱綅绗︾殑鏇挎崲鍊?var params ={
    id = jsonData.id;
}
var result = jsonStore[ params ].delete()
console.log("鍒狅紝浠?DELETE 鏂规硶璇锋眰缃戝潃",http.lastRequestUrl)

console.dump(result)
console.pause()

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Web/REST/jsonClient.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Web/REST/jsonClient.md')

