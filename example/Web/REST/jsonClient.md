[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: web.rest 客户�?- web.rest.jsonClient

```aardio aardio
//web.rest 客户�?- web.rest.jsonClient
import console;
import web.rest.jsonClient;

console.showLoading("正在连接JSON数据�?);
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
console.log("增，�?POST 方法请求网址",http.lastRequestUrl)

var result = jsonStore[jsonData.id].put(
    name = "jon.snow2";
    age = 32;
)
console.log("改，�?PUT 方法请求网址",http.lastRequestUrl)

var result = jsonStore[jsonData.id].patch(
    name = "jon.snow3";
)
console.log("部分修改，以 PATCH 方法请求网址",http.lastRequestUrl)

//也可以在网址中使用大括号指定占位�?var jsonStore = http.api("https://extendsclass.com/api/json-storage/bin/{id}");

//API对象的成员名会被自动按顺序替换为URL占位符（忽略占位符的名字�?var result = jsonStore[jsonData.id].get();
console.log("查，�?GET 方法请求网址",http.lastRequestUrl)
console.dumpJson(result)

//也可以用一个表指定多个占位符的替换�?var params ={
    id = jsonData.id;
}
var result = jsonStore[ params ].delete()
console.log("删，�?DELETE 方法请求网址",http.lastRequestUrl)

console.dump(result)
console.pause()

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Web/REST/jsonClient.md)

