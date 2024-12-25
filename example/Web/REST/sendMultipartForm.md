[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: �?web.rest 客户端调�?HTTP API - 上传文件表单

```aardio aardio
//�?web.rest 客户端调�?HTTP API - 上传文件表单
import console;
import web.rest.jsonLiteClient;

//创建 REST 客户�?var http = web.rest.client();

//声明 HTTP API
var ftEllo = http.api("https://fontello.com");

//使用文件表单上传文件，可以指定多个字�?var sessionId = ftEllo.sendMultipartForm( {
    //文件路径前必须添�?@ 字符
    //如果文件不存在这个函数会忽略字段（不会报错）�?    config = "@\fontello_config.json";
});
//上面代码也可以写�?fontello.post.sendMultipartForm();

//也可以如下指定上传进度回调函数，contentLength 为要上传的总长度，sendSize 为已上传的长度�?var sessionId = ftEllo.sendMultipartForm( {
        config = "@\config.json";
    },function(sendData,sendSize,contentLength,remainSize){
        /*
        sendData 为本次上传数据；
        sendSize 为本次上传字节数�?        contentLength 为要上传的总字节数�?        remainSize 为剩余字节数�?        */
        console.log("正在上传",sendSize,contentLength);
    }
);

if(sessionId){
    //下载字体文件
    import console.progress;
    var bar = console.progress();
    bar.recvSize = 0;

    ftEllo[sessionId].receiveFile("/fontello.zip",function(recvData,recvSize,contentLength){

        //计算下载进度
        bar.recvSize = bar.recvSize + recvSize;
        var p = bar.recvSize / contentLength * 100;

        //在控制台显示下载进度
        bar.setProgress(p,p +"% 已下�?......");
    }).getGet();

    //import process;
    //var url = ftEllo[sessionId].getUrl();
    //process.execute(url)
}

console.pause(true);

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Web/REST/sendMultipartForm.md)

