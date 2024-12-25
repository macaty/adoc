[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 上传

```aardio aardio
//上传
import console;
import inet.http;

console.open();
console.setTitle("正在上传...");

var http = inet.http();
http.beginRequest( "http://eu.httpbin.org/post","POST" );

//循环上传
http.beginSendData(100)
for(i=1;100;1){
    http.writeData( "-" )
    io.stdout.write(".")
}
http.endSendData()

//循环下载
file = io.file("/test.html","w+b")
for(str,size in http.eachRead() ){
    file.write( str );
    io.stdout.write( str )
}

io.print("ok")
execute("pause")

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Network/Transfer/stream.md)

