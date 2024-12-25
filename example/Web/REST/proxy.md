[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: �?web.rest 客户端调�?HTTP API - 设置代理服务�?
```aardio aardio
//�?web.rest 客户端调�?HTTP API - 设置代理服务�?import console;
import inet.ipdata;
import web.rest.jsonClient;

//第二个构造参数指定代理服务器
//代理配置格式: https://www.aardio.com/zh-cn/doc/library-guide/std/inet/proxy.html
var http = web.rest.jsonClient(,"socks=127.0.0.1:1081");

//声明 HTTP 接口对象
//声明 API，参�?@3 指定的模式串用于匹配返回数据
var api = http.api("http://myip.ipip.net",,"(\d+\.\d+\.\d+\.\d+)");

//发�?GET 请求
var ip = api.get();

//显示 IP 所在地
console.log( inet.ipdata().query(ip) )
console.pause(true);

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Web/REST/proxy.md)

