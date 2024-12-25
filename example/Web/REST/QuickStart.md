[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: �?web.rest 客户端调�?HTTP API - 入门

```aardio aardio
//�?web.rest 客户端调�?HTTP API - 入门
import console;
console.showLoading(" 正在连接服务�?)

import web.rest.jsonLiteClient;

/*
创建 HTTP( REST ) 客户端�?请求为网页表单编码，响应数据直接返回，使�?web.rest.client
请求为网页表单编码，响应数据�?JSON，使�?web.rest.jsonLiteClient
请求与响应数据都�?JSON，使�?web.rest.jsonClient

web.rest 入门教程�?https://www.aardio.com/zh-cn/doc/library-guide/std/web/rest/client.html
*/
var http = web.rest.jsonLiteClient();

//声明 HTTP 接口对象
var api = http.api("http://httpbin.org/anything/")

/*
调用 HTTP 接口函数（已经自动转换为了本地函数）�?返回 JSON 自动转换为了 aardio 对象�?*/
var ret = api.object.method({
    name = "用户�?;
    data = "其他数据";
});

/*
上面的函数自动做了几件事�?
1、将 api.object.method 的请求网址自动转换�?"http://httpbin.org/anything/object/method"
HTTP 接口对象的每个下级成员名都追加在网址尾部

2、将函数参数按表单编码转换为字符串提交�?
3、解析服务器返回�?JSON ，并作为函数返回值返回�?*/

//发�?GET 请求
var ret = api.name.get( a = 1,b = 2);

//发�?POST 请求
//var ret = api.name.post( a = 1,b = 2);

//发�?PATCH 请求
//var ret = api.name.patch( a = 1,b = 2);

//发�?PUT 请求
//var ret = api.name.put( a = 1,b = 2);

//发�?DELETE 请求
//var ret,err = api.name.delete( a = 1,b = 2);

//第一个返回值可转换为逻辑真表�?API 调用成功
if(ret){
    //输出服务端返回对�?—�?这个接口返回的是 HTTP 请求信息
    console.dumpJson(ret);
}
else {
    //err 为错误信息（字符串）
    console.log(err) //可能为本地错误，也可能是服务器应答的错误信息

    /*
    返回服务器应答的错误对象，如果也是此客户端可解析的响应格式（这里�?JSON ）则解析并返回解析结果�?    如果发生了其他错误，服务器并未应答则返回 null �?    如果请求成功则返�?null �?    */
    var errObject = http.lastResponseError();

    //也要吧指定要返回的字段，如果找不到返�?null ，不会抛出异�?    var errorMessage = http.lastResponseError("error");
}

console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Web/REST/QuickStart.md)

