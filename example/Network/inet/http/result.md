[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 返回�?
```aardio aardio
//返回�?import console;
import inet.http;

//创建 HTTP 对象
var http = inet.http();

//http 对象发送请求的函数基本都有 3 个返回值：响应数据,错误信息,错误代码
var data,err,errCode = http.post( "http://eu.httpbin.org/post"
    ,"username=user&password=pwd" );

if( data ){
    console.log(data);
}
else {
    if( http.statusCode ){
        //服务端返回错误信�?        console.log( http.lastResponse(), "HTTP错误代码:" + http.statusCode )
    }
    else{
        //本地内部错误
        console.log( err,errCode );
    }
}

http.close();
console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Network/inet/http/result.md)

