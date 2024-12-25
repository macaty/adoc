[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 .NET 创建 WebService 客户�?
```aardio aardio
//aardio 调用 .NET 创建 WebService 客户�?import console;
import dotNet;

//动态创�?WebService
var wsAssembly = dotNet.createWebService("http://fy.webxml.com.cn/webservices/EnglishChinese.asmx")

//调用 WebService 类创建对�?var englishChinese = wsAssembly.new("EnglishChinese")

//调用 WebService 提供的函�?var ret = englishChinese.TranslatorString("hello" );

console.dump(ret);

console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/Advanced/WebService.md)

