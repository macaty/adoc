[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 发�?JSON

```aardio aardio
//发�?JSON
import inet.http;
import web.rest.jsonClient;
import web.json;

import console.int;
console.showLoading(" 正在发送请�?);

//创建 HTTP 客户端对�?var http = inet.http();

//发�?POST 请求，如�?POST 数据�?JSON 则自动设�?JSON 请求�?var data = http.post("http://eu.httpbin.org/post",
    web.json.stringify({ username = "user"; password = "pwd" })
);

/*
改用 web.rest.jsonClient 更简单，
发送表参数可自动转换为 JSON，返�?JSON 也可自动解析为表�?*/
var http = web.rest.jsonClient();
var data = http.post("http://eu.httpbin.org/post"
    ,{ username = "user"; password = "pwd" } );

//更多范例请参考：\范例程序\Web 应用\REST
console.dumpJson(data);

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Network/inet/http/json.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Network/inet/http/json.md')

