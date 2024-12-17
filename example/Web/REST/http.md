[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: �?web.rest 创建 HTTP 客户�?
```aardio aardio
//�?web.rest 创建 HTTP 客户�?import console;
import web.rest.jsonClient;
console.showLoading("正在连接服务�?)

//创建 HTTP 客户�?var http = web.rest.jsonClient();

//发�?GET 请求
var ret = http.get("http://httpbin.org/anything",{
    name = "用户�?;
    data = "其他数据";
})
console.dumpJson(ret);

//发�?POST 请求
var ret = http.post("http://httpbin.org/anything",{
    name = "用户�?;
    data = "其他数据";
})

//示例 JSON
var json = /*
{
    "data":"其他数据",
    "name":"用户�?
}
*/

//如果提交数据是字符串，则不作任何转换直接发�?var ret = http.post("http://httpbin.org/anything",json)

console.dumpJson(ret);
console.pause();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Web/REST/http.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Web/REST/http.md')

