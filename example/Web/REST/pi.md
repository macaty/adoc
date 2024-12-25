[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: �?web.rest 客户端调�?HTTP API - 获取圆周�?
```aardio aardio
//�?web.rest 客户端调�?HTTP API - 获取圆周�?import console.int;
import web.rest.jsonLiteClient;

var http = web.rest.jsonLiteClient();

//可查询前 100 万亿位的圆周率，也是目前最长的在线可用圆周率数据库之一
var delivery = http.api("https://api.pi.delivery/v1/pi");

//查询圆周率，参数指定一个表对象（table），单个表参数外层的 {} 可以省略不写
var ret = delivery.get(
    start=1, //从第 1 位开�?    numberOfDigits=100 //返回 100 位圆周率
)

//显示圆周�?console.log("3."+ ret.content)

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Web/REST/pi.md)

