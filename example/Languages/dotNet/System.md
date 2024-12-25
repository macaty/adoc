[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 导入 .NET 名字空间

```aardio aardio
//aardio 导入 .NET 名字空间
import dotNet;

//导入  .NET 名字空间，参�?@2 指定程序集名字（与名字空间相同时可省略）�?dotNet.import("System"); //System 其实已自动导入，这里只是用来举例�?
/*
访问下级 .NET 名字空间、类、枚举时，可通过触发元方法自动导入（必须在同一程序集内）�?注意打开名字空间�?namespace 语句不会触发元方法，�?with 语句可以�?*/
var uri = System.Uri("http://www.aardio.com");

/*
aardio 会优先搜索加�?.NET 名字空间的程序集�?如果找不到类型，则会全局搜索所有已加载的程序集�?�?System.dll,mscorlib.dll 属于默认加载的系统程序集�?
当然，也可以象下面这样自指定程序集加载下级名字空间（�?aardio 新版本中不是必须的）�?*/
dotNet.import("System.Security.Cryptography","mscorlib");

/*
上级名字空间自动导入下级名字空间，反之不行�?不会自动导入或替换上级名字空间，例如下面的代码不能替�?dotNet.import("System");
*/
dotNet.import("System.Security.Cryptography.X509Certificates","System");

//============================================================================

//重复导入同一名字空间被忽略，不报�?dotNet.import("System"); //可用 System.__assembly 得到导入该名字空间的程序�?
/*
如果从不同的程序集导入相同的 .NET 名字空间�?则不会替换已导入�?.NET 名字空间，只能从返回值获取导入的名字空间�?
重复导入通常是不必要的，aardio 会从所有已加载的程序集搜索名字空间与类型�?*/
var SystemCore = dotNet.import("System","mscorlib");

//============================================================================
//.NET 名字空间�?.NET 规范命名，aardio 名字空间则统一为首字母小写的小驼峰规范�?
//aardio 已经提供了一些库可用于导�?.NET 名字空间，例如：
import System.IO;

/*
创建 System.IO.FileStream 对象实例�?因为 System.IO 库已经预处理了路径参数�?所以不需要再调用 io.fullpath 转换�?*/
var fs = System.IO.File.Create( "/.testStream.txt" );

//也可以这样写，支�?aardio 兼容的读写模�?//var fs = System.IO.FileStream("/.testStream.txt","w+");

//buffer 相当�?.NET 中的字节数组
var buf = raw.buffer("测试一�?);
fs.Write(buf,0,#buf);
fs.Close();

import win.dlg.message;
win.dlg.message().doModal(string.load("/.testStream.txt"));

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/System.md)

