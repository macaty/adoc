[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# wsock.networkChange 库模块帮助文�?
## wsock.networkChange 成员列表

检测网络变更，例如启用或禁用网�?
### wsock.networkChange.wait()

等待网络变更，例如启用或禁用网卡�?
此函数不能用于获取网络连接状�?

可使�?inet.http.isAlive,inet.ras.isAlive 等检测网络连接状�?
[返回对象:wsockNetworkChangeObject](#wsockNetworkChangeObject)

### wsock.networkChange.wait(winform)

等待网络变更，例如启用或禁用网卡�?
参数可指定回调窗口或控件对象,

网络变更时回调窗口或控件的成员函�?onNetworkChanged

此函数返回参数@1

## wsockNetworkChangeObject 成员列表

### wsockNetworkChangeObject.onNetworkChanged

```aardio aardio
wsockNetworkChangeObject.onNetworkChanged = function(){
    var ip = wsock.tcp.client.test(); /*网络已变更，
获取上网�?IP 成功则为连接网络，否则为断开网络*/
}

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/wsock/networkChange.md)

