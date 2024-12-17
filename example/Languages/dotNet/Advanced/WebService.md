[aardio 鏂囨。](../../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 璋冪敤 .NET 鍒涘缓 WebService 瀹㈡埛绔?
```aardio aardio
//aardio 璋冪敤 .NET 鍒涘缓 WebService 瀹㈡埛绔?import console;
import dotNet;

//鍔ㄦ�佸垱寤?WebService
var wsAssembly = dotNet.createWebService("http://fy.webxml.com.cn/webservices/EnglishChinese.asmx")

//璋冪敤 WebService 绫诲垱寤哄璞?var englishChinese = wsAssembly.new("EnglishChinese")

//璋冪敤 WebService 鎻愪緵鐨勫嚱鏁?var ret = englishChinese.TranslatorString("hello" );

console.dump(ret);

console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/Advanced/WebService.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/Advanced/WebService.md')

