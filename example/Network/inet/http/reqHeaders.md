[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 请求�?
```aardio aardio
//请求�?import console;
import inet.http;

console.showLoading(" 正在发送请�?);

//创建 HTTP 客户端对�?var http = inet.http();

/*
inet.http 所�?HTTP 请求头属性、参数都可以
使用 web.joinHeaders() 函数支持的字符串、表（数组、键值对）�?*/

//设置所有请求默认添加的 HTTP 头，请求结束不清�?http.addHeaders = "Name1:value1";

//可选在 beforeSend 事件回调内写 HTTP 请求头�?http.beforeSend = function(){
    http.writeHeader("Name2:value2"); //�?HTTP 请求�?}

//发�?GET 请求,可选用 参数 @2 自定�?HTTP 请求�?//var data  = http.get("http://www.httpbin.org/get",{ "Accept-Language":"zh-CN,zh"; });

//发�?POST 请求,可选用参数 @3 自定�?HTTP 请求�?var data = http.post("http://www.httpbin.org/post", ,{
    "Accept-Language":"zh-CN,zh";
    "User-Agent":"abc"
});

//显示服务器返回的数据
console.log(data);

//关闭对象�?http.close();

console.pause(true);

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Network/inet/http/reqHeaders.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Network/inet/http/reqHeaders.md')

