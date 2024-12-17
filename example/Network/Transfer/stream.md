[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 涓婁紶

```aardio aardio
//涓婁紶
import console;
import inet.http;

console.open();
console.setTitle("姝ｅ湪涓婁紶...");

var http = inet.http();
http.beginRequest( "http://eu.httpbin.org/post","POST" );

//寰幆涓婁紶
http.beginSendData(100)
for(i=1;100;1){
    http.writeData( "-" )
    io.stdout.write(".")
}
http.endSendData()

//寰幆涓嬭浇
file = io.file("/test.html","w+b")
for(str,size in http.eachRead() ){
    file.write( str );
    io.stdout.write( str )
}

io.print("ok")
execute("pause")

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Network/Transfer/stream.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 服务器报告访问的文件是隐藏的。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Network/Transfer/stream.md')

