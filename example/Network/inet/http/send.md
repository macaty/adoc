[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 分步请求

```aardio aardio
//分步请求
import console;
import inet.http;

//首先创建 HTTP 客户端对�?var http = inet.http();

//创建 HTTP 请求，参�?@2指定请求方法，更多参数请查看函数说明
http.beginRequest("http://www.aardio.com","GET");

//发送请�?http.send();

//读取 HTTP 响应头（要在发送请求头后才能读�?）�?var headers = http.readHeader();
console.log(headers);

//读取数据
var data = http.readAll();
console.log(data);
console.pause()

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Network/inet/http/send.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Network/inet/http/send.md')

