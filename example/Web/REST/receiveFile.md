[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: �?web.rest 客户端调�?HTTP API - 下载文件

```aardio aardio
//�?web.rest 客户端调�?HTTP API - 下载文件
import console;
import web.rest.jsonLiteClient;

//创建 REST 客户�?var http = web.rest.client();

//声明 HTTP API
var aardio = http.api("https://www.aardio.com");

/*
下载文件:
如果创建文件失败 receiveFile 函数会返�?null 及错误信息，否则返回对象自身�?*/
var ok = aardio.receiveFile("/.test.html").get();

/*
可选如下指定下载进度回调函数：
要切�?receiveFile 指定的下载参数仅对本次请求有效�?*/
aardio.receiveFile("/.test.html",function(recvData,recvSize,contentLength){
    /*
    recvData 为当前下载数据�?    recvSize 为当前下载数据字节数�?    contentLength 为需要下载的总字节数�?    */
    console.log(,recvSize,contentLength)
}).get();

console.pause();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Web/REST/receiveFile.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Web/REST/receiveFile.md')

