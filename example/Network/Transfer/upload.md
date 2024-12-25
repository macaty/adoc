[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 上传文件

```aardio aardio
//上传文件
import console.int;
import console.progress;
import web.rest.jsonLiteClient;

var http = web.rest.jsonLiteClient();
var api = http.api("https://httpbin.org/post");

//进度�?var bar = console.progress();

//使用文件表单上传文件，可以指定多个字�?var result = api.sendMultipartForm( {
        file = "@\b.upload.aardio";
    },function(sendData,sendSize,contentLength,remainSize){
        /*
        sendData 为本次上传数据；
        sendSize 为本次上传字节数�?        contentLength 为要上传的总字节数�?        remainSize 为剩余字节数�?        */

        bar.setProgress((1 - remainSize/contentLength) * 100,"正在上传 ......");
    }
);

console.dumpJson(result);

//直接上传文件
var api = http.api("https://httpbin.org/anything");
var result = api.sendFile( "\b.upload.aardio"
    ,function(sendData,sendSize,contentLength,remainSize){
        /*
        sendData 为本次上传数据；
        sendSize 为本次上传字节数�?        contentLength 为要上传的总字节数�?        remainSize 为剩余字节数�?        */
    }
);

console.dumpJson(result);

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Network/Transfer/upload.md)

