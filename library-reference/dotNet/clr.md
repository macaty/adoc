[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# dotNet.clr 库模块帮助文�?
## dotNet 成员列表

支持�?

### dotNet.clr("v4.0")

创建 CLR 运行�?

可以使用多个参数指定多个允许加载的版本号,

不指定参数可以自动选择合适的版本,

如果之前已成功创建此对象,则会使用之前指定�?.Net 运行时版�?

注意 .NET 3.5 �?CLR 运行时是 v2.0,.Net 4.x �?CLR 运行时是 v4.0,

Win7 自带 CLR 2.0运行�?Win10,Win11 自带 CLR 4.0 运行�?
aardio 可以自适应 CLR 2.0/4.0，对 .Net 版本没有严格要求�?
一般不需要自己去创建应用程序域，例如加载程序集，直接�?
dotNet.load �?dotNet.loadFile 就可�?
### dotNet.clr()

[返回对象:dotNetClrObject](#dotNetClrObject)

## dotNetClrObject 成员列表

### dotNetClrObject.createAppDomain("域名�?)

创建应用程序�?参数可�?
如果尚未创建默认单例应用程序域，

则不指定 @domainName 参数时创建并返回为默认单例应用程序域�?
无参数调�?dotNet.appDomain 总是返回默认单例应用程序域，

引入 dotNet 库也会自动创建默认应用程序域

### dotNetClrObject.createAppDomain()

[返回对象:dotNetAppDomainObject](#dotNetAppDomainObject)

### dotNetClrObject.majorVersion

CLR 运行时版本号，数值�?
只有可能�?2 �?4，不会有其他主版本�?
注意 CLR 版本不完全等�?.NET 版本

获取完整 CLR 版本号或检�?.NET Framework 版本请查�?
aardio 提供�?System.Environment.Version �?
### dotNetClrObject.runtimeHost

[返回对象:dotNetCorRuntimeHostObject](#dotNetCorRuntimeHostObject)

### dotNetClrObject.version

CLR 运行时版本�?
这个值只有可能是 "v2.0.50727" �?"v4.0.30319"�?
注意 CLR 版本不完全等�?.NET 版本

获取完整 CLR 版本号或检�?.NET Framework 版本请查�?
aardio 提供�?System.Environment.Version �?
## dotNetClrObject.AppDomainSetup 成员列表

### dotNetClrObject.AppDomainSetup.ApplicationBase

获取或设置包含该应用程序的目录的名称�?
### dotNetClrObject.AppDomainSetup.ApplicationName

获取或设置应用程序的名称�?
### dotNetClrObject.AppDomainSetup.CachePath

获取和设置特定于应用程序的区域名�?在该区域中影像复制文件�?
### dotNetClrObject.AppDomainSetup.ConfigurationFile

获取和设置应用程序域的配置文件的名称�?
### dotNetClrObject.AppDomainSetup.DynamicBase

获取或设置将在其中存储和访问动态生成文件的目录�?
### dotNetClrObject.AppDomainSetup.LicenseFile

获取或设置与此域关联的许可证文件的位置�?
### dotNetClrObject.AppDomainSetup.PrivateBinPath

获取或设置目录列�?它与 ApplicationBase 目录结合来探测专用程序集�?
### dotNetClrObject.AppDomainSetup.PrivateBinPathProbe

获取或设置用于定位应用程序的专用二进制目录路径�?
### dotNetClrObject.AppDomainSetup.ShadowCopyDirectories

获取或设置目录的名称,这些目录包含要影像复制的程序集�?
### dotNetClrObject.AppDomainSetup.ShadowCopyFiles

获取或设置指示影像复制是打开还是关闭的字符串

## dotNetCorRuntimeHostObject 成员列表

### dotNetCorRuntimeHostObject.Stop()

停止 .Net 运行�?
[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/dotNet/clr.md)

