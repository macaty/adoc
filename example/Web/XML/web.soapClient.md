[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: SOAP WebService

```aardio aardio
//SOAP WebService
import console;

//导入MSSOAP支持�?import web.soapClient;

//创建SOAP客户�?seviceClient = web.soapClient("http://fy.webxml.com.cn/webservices/EnglishChinese.asmx")

//调用远程Web服务提供的函�?var transArray,err =  seviceClient.TranslatorString("hello");

//显示返回�?console.dump( string.join( transArray,'\r\n' ) ) ;

//按任意键继续
console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Web/XML/web.soapClient.md)

