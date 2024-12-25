[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: �?web.rest 客户端调�?HTTP API - 自动模式匹配

```aardio aardio
//�?web.rest 客户端调�?HTTP API - 自动模式匹配
import console;
console.showLoading("获取外网IP");

import web.rest.client;
var http = web.rest.client();

//声明 API，参�?@3 指定的模式串用于匹配返回数据
var api = http.api("http://myip.ipip.net",,"(\d+\.\d+\.\d+\.\d+)");

//调用 HTTP 接口
var ip = api.get();

//显示查询结果
console.log( ip  );

console.pause(true);

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Web/REST/match.md)

