[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: SOAP WebService

```aardio aardio
//SOAP WebService
import console;

//瀵煎叆MSSOAP鏀寔搴?import web.soapClient;

//鍒涘缓SOAP瀹㈡埛绔?seviceClient = web.soapClient("http://fy.webxml.com.cn/webservices/EnglishChinese.asmx")

//璋冪敤杩滅▼Web鏈嶅姟鎻愪緵鐨勫嚱鏁?var transArray,err =  seviceClient.TranslatorString("hello");

//鏄剧ず杩斿洖鍊?console.dump( string.join( transArray,'\r\n' ) ) ;

//鎸変换鎰忛敭缁х画
console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Web/XML/web.soapClient.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Web/XML/web.soapClient.md')

