[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# .NET 运行�?
## 创建 .NET 应用程序�?[\#](\#appDomain)

应用程序域是 .NET 里的程序隔离边界�?一个进程可以包含多个应用程序域。在 aardio 中应用程序域就是 dotNet.appDomain 对象�?
�?aardio 创建 .NET 应用程序域的完整代码如下（不必要这么做）�?
```aardio aardio
//加载 CLR 运行�?var clr = dotNet.clr("v4.0")

//创建应用程序域，可选在参数中指定域名称
var appDomain = clr.createAppDomain()

//加载 .NET 程序�?var SystemAssembly = appDomain.load("System");

//加载 .NET 名字空间
var System = dll.import("System");

//卸载应用程序�?appDomain.unload()

```

但是一般我们不需要写上面这些复杂的代码�?
- aardio 自动并管理独创建应用程序域�?- aardio 可以自适应所�?.NET 版本�?
具体到用法：

- 如果无参数调�?dotNet.appDomain() 不会创建新的应用程序域，而是在同一线程始终返回相同的实例。这个单例应用程序域不需要也不会卸载，线程结�?aardio 才会自动卸载这个应用程序域�?- 我们甚至不必要去调用 dotNet.appDomain()，aardio 会自动帮我们调用�?
所以上面的代码我们可以简化如下：

```aardio aardio
dotNet.load("System").import("System");

```

dotNet.load 导入程序集，�?.NET 程序集对象提�?import 函数加载 .NET 名字空间。当程序集与导入�?.NET 名字空间相同时，我们可以进一步简化上面的代码为：

```aardio aardio
dotNet.import("System");

```

因为 aardio 提供�?System 标准库用于执行上面的代码�?
所以我们可以简写为�?
```aardio aardio
import System;

```

实际上面的代码我们都不用写，因为导入 dotNet 库时会自动导�?.NET �?System 名字空间�?
.NET 作为一个大型框架，需要考虑各种情况，有很多步骤和参数，
但是 aardio 的目标则是只要简洁，不求完美�?
## .NET 运行时版�?[\#](\#versions)

### aardio 自动兼容 .NET CLR 2.0 / 4.0

NET 虽然有很多版本，但核心运行时只有 CLR 2.0 �?CLR 4.0 的区别。如�?C# 代码使用了一些非常新�?C# 语法 —�?�?VS 编译�?DLL 以后�?CLR 4.0 下运行时没有问题的�?
aardio 可以自动兼容 CLR 2.0 / CLR 4.0 编写的程序集�?aardio + .NET 开发有更好的兼容性，�?.NET 版本没有严格要求，可以重用大量的 .NET 组件�?并且可以编写出体积小、不依赖非系�?DLL 的独�?EXE 文件（也可以内存加载外部程序集）

系统自带的都�?.NET Framework �?如果安装 NuGet 包时找不�?.NET Framework 的程序集�?那么可以改用 NET Standard 2.0 的程序集�?
�?.NET Framework 4.5 及以�?起支�?NET Standard 1.0�?�?.NET Framework 4.6.1 起支�?NET Standard 2.0�?但实际上 NET Standard 2.0 推荐的最低版本是 .NET 4.7.2 �?
### 各操作系统自�?.NET 版本

- Windows 7 自带 .NET 3.5.1，支�?lambda
- Windows 8 自带 .NET 3.5.1 + .NET 4.5
- Windows 10 自带 .NET 4.6 �?NET 4.x 支持 dynamic 对象 + 异步任务�?NET 4.5 支持 task.Run
- Windows 10 1511 自带 .NET 4.6.1
- Windows 10 1607 自带 .NET 4.6.2 �?- Windows 10 1709 自带 .NET 4.7.1 ，支�?ValueTuple
- Windows 0 1809 自带 .NET 4.7.2
- Windows 11 以及 Win10 1903 自带 .NET 4.8

参考： [.NET 版本和依赖关系](javascript:if(confirm('https://learn.microsoft.com/zh-cn/dotnet/framework/migration-guide/versions-and-dependencies  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ����һ������·���ⲿ������Ϊ������ʼ��ַ�ĵ�ַ��  \n\n�����ڷ������ϴ�����?'))window.location='https://learn.microsoft.com/zh-cn/dotnet/framework/migration-guide/versions-and-dependencies')

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-guide/std/dotNet/clr.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-guide/std/dotNet/clr.md')

