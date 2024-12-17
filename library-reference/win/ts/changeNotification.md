[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# win.ts.changeNotification 库模块帮助文�?
## win.ts 成员列表

### win.ts.changeNotification

监听用户对桌面会话的操作

### win.ts.changeNotification()

[返回对象:wtsChangeNotificationObject](#wtsChangeNotificationObject)

### win.ts.changeNotification(窗口对象)

注册文件监听窗口\\监听用户对桌面会话的操作,

省略参数则创�?message only window

## wtsChangeNotificationObject 成员列表

### wtsChangeNotificationObject.\_form

[返回对象:winform](../ui/_.html#winform)

### wtsChangeNotificationObject.deregister()

注销并关闭监�?
### wtsChangeNotificationObject.onSessionChange

```aardio aardio
wtsChangeNotificationObject.onSessionChange = function(sessionId,statusText,statusCode){
    /*桌面会话改变，：例如用户登录，远程桌面连接断开�?/
}

```

### wtsChangeNotificationObject.register(选项)

注册并启用文件监视功�?

所有参数都可以省略,默认�?\_NOTIFY\_FOR\_ALL\_SESSIONS 选项

### 自动完成常量

\_NOTIFY\_FOR\_ALL\_SESSIONS=1

\_NOTIFY\_FOR\_THIS\_SESSION=0

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/win/ts/changeNotification.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/win/ts/changeNotification.md')

