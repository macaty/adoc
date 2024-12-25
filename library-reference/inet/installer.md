[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# inet.installer 库模块帮助文�?
## inet 成员列表

### inet.installer(appName,url,parameters,savePath,winform)

下载并启动安装程�?以管理权限启动安�?

@appName 参数下载窗口标题显示的应用程序名,

@url 参数为下载地址,允许传入一个动态返�?url 的线程函�?

@url 参数也可以传入一个表,使用x64,x86键值分别指�?4位�?2位系统下载网址�?
@parameters 参数为运行安装程序的参数,可选参�?

@savePath 参数为存储路�?可选参�?

@winform 用于指定父窗�?可选参�?
用户阻止安装程序以管理权限启动返回false,成功启动并关闭返回true

返回true并不表明安装过程中没有出�?
## inet.installer 成员列表

下载并启动安装程�?
通常启动安装程序加上 /? 参数可以查看该安装程序支持的参数

### inet.installer.asInvoker(appName,url,parameters,savePath,winform)

下载并启动安装程�?以当前进程权限启动安�?

@appName 参数下载窗口标题显示的应用程序名,

@url 参数为下载地址,允许传入一个动态返�?url 的线程函�?

@parameters 参数为运行安装程序的参数,可选参�?

@savePath 参数为存储路�?可选参�?

@winform 用于指定父窗�?可选参�?
安装程序未正常启动返回false,成功启动并关闭返回true

返回 true 并不表明安装过程中没有出�?
[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/inet/installer.md)

