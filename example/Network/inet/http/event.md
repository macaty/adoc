[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 事件回调

```aardio aardio
//事件回调

import console;
import inet.http;

//首先创建 HTTP 客户端对�?var http = inet.http();

//准备向服务器发送数据时执行此回�?http.beforeSend = function(){

}

//发送请求以后，获取数据以前执行此回�?http.afterSend = function(statusCode,contentLength){

    /*
    如果在这里不带参数读取了所�?HTTP 头，
    �?aardio 会缓存所�?HTTP 头，即使请求结束仍然可以使用 http.readHeader 函数�?    */
    http.readHeader();
}

//发�?GET 请求并获取数�?var data = http.get("http://www.aardio.com")
console.log(data);

/*
如果在请求前读取过全�?HTTP 头，即使请求结束仍然可以使用 http.readHeader 函数�?*/
console.log(http.readHeader());
console.pause()

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Network/inet/http/event.md)

