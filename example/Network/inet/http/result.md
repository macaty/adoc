[aardio 鏂囨。](../../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 杩斿洖鍊?
```aardio aardio
//杩斿洖鍊?import console;
import inet.http;

//鍒涘缓 HTTP 瀵硅薄
var http = inet.http();

//http 瀵硅薄鍙戦�佽姹傜殑鍑芥暟鍩烘湰閮芥湁 3 涓繑鍥炲�硷細鍝嶅簲鏁版嵁,閿欒淇℃伅,閿欒浠ｇ爜
var data,err,errCode = http.post( "http://eu.httpbin.org/post"
    ,"username=user&password=pwd" );

if( data ){
    console.log(data);
}
else {
    if( http.statusCode ){
        //鏈嶅姟绔繑鍥為敊璇俊鎭?        console.log( http.lastResponse(), "HTTP閿欒浠ｇ爜:" + http.statusCode )
    }
    else{
        //鏈湴鍐呴儴閿欒
        console.log( err,errCode );
    }
}

http.close();
console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Network/inet/http/result.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 服务器报告访问的文件是隐藏的。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Network/inet/http/result.md')

