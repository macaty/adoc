[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 API

```aardio aardio
//调用 API
import curl;
import console;

var http = curl.easy();//创建客户�?
//POST演示
console.showLoading("正在连接网页");
var str = http.post("http://httpbin.org/post"
        ,"username=jacen&password=123456");
console.log(str);

//参数也可以指定一个表
var str = http.post("http://httpbin.org/post" ,{
    username = "jacen";
    password="123456";
});
console.log(str);

//GET演示
var str = http.get("http://www.aardio.com");
console.log(str);

/*
更多用法请参考：
https://bbs.aardio.com/forum.php?mod=viewthread&tid=9319

更推荐使�?web.rest （体积小，基于系统自带组件，用法更简单）
https://mp.weixin.qq.com/s/4mYRDnO49alwpQoBD_cILg

或使�?inet.http  （体积小，基于系统自带组件，用法更简单）
https://mp.weixin.qq.com/s/3Xp4c1LxsOQJsux5o8bhvA
*/

console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Network/curl/libcurl.md)

