[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 .NET 之控制台操作

```aardio aardio
//aardio 调用 .NET 之控制台操作
import dotNet;
var compiler = dotNet.createCompiler("C#");

compiler.Source = /***
using System;
namespace CSharpLibrary
{
    public class Object
    {
        public static void Test(){
            System.Console.WriteLine("这是 C# 在控制台输出的内�?);
        }
    }
}
***/
compiler.import("CSharpLibrary");

import console
console.log("只要调用 console 库打开控制台，就会自动绑定 .NET 控制台�?)

/*
console 库函数会自动调用 console.open() 打开控制台�?如果控制�?console 库被打开，aardio 就会自动绑定 .NET 控制台�?*/
CSharpLibrary.Object.Test();

/*
console 打开控制台以后会向同一线程发�?"afterConsoleOpen" 事件�?订阅此事件就可以绑定控制台，以下是标准库 dotNet.appDomain 中的相关代码�?
var reopenConsole = function(){

    for(k,appDomain in __appDomainCache){
        // ..io.utf8 用于判断R控制台是�? UTF-8 编码�?        // aardio �? Win10 1709 以上会将控制台默认设�?UTF-8 编码�?        appDomain.utility.ReopenConsole(!!..io.utf8);
    }
}
if(::Kernel32.GetConsoleWindow()) reopenConsole();
..subscribe("afterConsoleOpen",reopenConsole);

当然，如果在导入 dotNet 库以前打开控制台，.Net 默认就会正确绑定�?这些代码主要是修正在导入 dotNet 库以后再打开控制台导�?.NET 不能在控制台输出输入的问题�?*/

console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/Apps/Console.md)

