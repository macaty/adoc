[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# zlib.installer 库模块帮助文�?
## zlib 成员列表

### zlib.installer(appName,url,parameters,savePath,x86exe,x64exe,winform)

下载压缩包并启动压缩包内安装程序,以管理权限启动安�?

@appName 参数下载窗口标题显示的应用程序名,

@url 参数为下载地址,

@parameters 参数为运行安装程序的参数,可选参�?

@savePath 参数为存储路�?可选参�?

@winform 用于指定父窗�?可选参�?
@x86exe 指定安装包中32位安装程序相对路径，

@x64exe 指定安装包中64位安装程序相对路径，可选参数，

用户阻止安装程序以管理权限启动返回false,成功启动并关闭返回true

返回true并不表明安装过程中没有出�?
## zlib.installer 成员列表

下载 _.zip、_.tar.gz、\*.tgz 文件并解压启动包内安装程�?
通常启动安装程序加上 /? 参数可以查看该安装程序支持的参数

### zlib.installer.asInvoker(appName,url,parameters,savePath,x86exe,x64exe,winform)

下载压缩包并启动压缩包内安装程序,以当前进程权限启动安�?

@appName 参数下载窗口标题显示的应用程序名,

@url 参数为下载地址,

@parameters 参数为运行安装程序的参数,可选参�?

@savePath 参数为存储路�?可选参�?

@winform 用于指定父窗�?可选参�?
@x86exe 指定安装包中32位安装程序相对路径，

@x64exe 指定安装包中64位安装程序相对路径，可选参数，

用户阻止安装程序以管理权限启动返回false,成功启动并关闭返回true

返回true并不表明安装过程中没有出�?
[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/zlib/installer.md)

