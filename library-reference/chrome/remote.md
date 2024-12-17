[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# chrome.remote 库模块帮助文�?
## chrome 成员列表

### chrome.remote

调用系统已安装的chrome创建应用程序,并启用远程调试端�?
### chrome.remote()

[返回对象:processchromeremoteObject](#processchromeremoteObject)

### chrome.remote(启动参数)

```aardio aardio
chrome.remote({
    ["--user-data-dir"] = "%LocalAppData%\aardio\chrome.remote.userdata";/*调用系统已安装的chrome创建应用程序,
同一用户数据目录应当只启动一个开启远程调试端口的浏览器进�?/
});

```

## processchromeremoteObject 成员列表

### processchromeremoteObject.chromeProcessId

启动的chrome进程ID

注意chrome会使用一个进程启动多个独立的应用

### processchromeremoteObject.hwndChrome

启动的chrome窗口句柄

### processchromeremoteObject.remoteDebuggingPort

远程调试端口

### processchromeremoteObject.userDataDir

用户数据目录,

如果开启远程调�?使用同一用户数据目录的chrome同时只能有一个进程实例运�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/chrome/remote.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/chrome/remote.md')

