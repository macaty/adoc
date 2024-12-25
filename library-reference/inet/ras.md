[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# inet.ras 库模块帮助文�?
## inet.ras 成员列表

### inet.ras.dial(连接参数)

```aardio aardio
inet.ras.dial(
    entryName =  "拔号连接�?;
    user =  "拔号用户�?;
    password = "拔号密码"
)

```

### inet.ras.eachEntry()

```aardio aardio
for name,flags,phonebook in inet.ras.eachEntry(){
    /*遍历拔号连接,name为连接名*/
}

```

### inet.ras.getConnection()

获取当前拔号连接,失败返回�?错误代码

[返回对象:rasconnObject](#rasconnObject)

### inet.ras.getEntries()

返回所有拔号连�?
### inet.ras.getEntry(参数�?

```aardio aardio
inet.ras.getEntry(
    entryName = "连接�?
)

```

### inet.ras.hangUp(连接句柄)

挂断

省略连接句柄则获取当前活动连�?
### inet.ras.isAlive()

返回两个�? 是否存在广域网连接（WAN�?是否存在局域网连接（LAN�?
### inet.ras.lasterr(错误代码)

返回错误信息,错误代码

### inet.ras.setCredentials(登录信息)

```aardio aardio
inet.ras.setCredentials(
    entryName = "连接�?;
    userName = "用户�?;
    password = "密码";
)

```

### inet.ras.setEntry(VPN连接参数)

```aardio aardio
inet.ras.setEntry(
    type = 2/*_RASET_Vpn*/;
    fOptions =  0x10/*_RASEO_RemoteDefaultGateway*/ | 0x100/*_RASEO_ModemLights*/ | 0x200/*_RASEO_SwCompression*/ | 0x800/*_RASEO_RequireMsEncryptedPw*/ | 0x1000000/*_RASEO_PreviewUserPw*/ | 0x400/*_RASEO_RequireEncryptedPw*/ | 0x20000000/*_RASEO_RequireMsCHAP2*/;
    fOptions2 = 0x2000000/*_RASEO2_CacheCredentials*/;
    ipaddrDns = "8.8.8.8";
    ipaddrDnsAlt = "1.1.1.1";
    vpnStrategy = 2/*_VS_PptpFirst*/;
    deviceType = "VPN";
    deviceName = "VPN";
    localPhoneNumber = "服务器地址";
    entryName = "VPN连接"
)

```

### inet.ras.setEntry(宽带连接参数)

```aardio aardio
inet.ras.setEntry(
    type = 5/*_RASET_Broadband*/;
    fOptions = 0x10/*_RASEO_RemoteDefaultGateway*/
        | 0x1000000/*_RASEO_PreviewUserPw*/
        | 0x4000000/*_RASEO_ShowDialingProgress*/
        | 0x100/*_RASEO_ModemLights*/
        | 0x100/*_RASEO2_ReconnectIfDropped*/ ;
    fOptions2 = 0x2000000/*_RASEO2_CacheCredentials*/
        | 4/*_RASEO2_DontNegotiateMultilink*/;
    deviceType = "PPPoE";
    deviceName = "WAN 微型端口 (PPPOE)";
    entryName = "ADSL宽带连接"
)

```

### inet.ras.setProxy("连接�?)

指定连接不使用代�?
### inet.ras.setProxy("连接�?,"SOCKS=代理服务器地址:端口","绕过代理地址")

省略连接名表示默认连接以及所有拔号连�?

设置SOCKS4代理服务�?不支持登�?
绕过代理地址可在域名或IP中使用通配�?多个以分号分�?
### inet.ras.setProxy("连接�?,"被代理协�?代理协议://主机地址:端口�?,"绕过代理地址")

省略连接名表示默认连接以及所有拔号连�?

参数@2可以直接写代理服务器域名或IP,

省略协议则默认为HTTP,省略端口则默认为80,

绕过代理地址可在域名或IP中使用通配�?多个以分号分�?
### inet.ras.setProxy()

默认连接以及所有拔号连接不使用代理

设置进程内代理请使用 inet.setProxy 函数

### inet.ras.setProxyAutoConfig("连接�?, "HTTP://主机地址:端口�?)

为指定连接设置自动配置代理（PAC）地址�?
省略连接名表示默认连接以及所有拔号连�?
### inet.ras.status()

[返回对象:rasconnstatusObject](#rasconnstatusObject)

### inet.ras.status(连接句柄)

返回拔号连接状态信�?
省略连接句柄则获取当前活动连�?
## rasconnObject 成员列表

### rasconnObject.deviceName

设备�?
### rasconnObject.deviceType

设备类型

### rasconnObject.entryName

连接�?
### rasconnObject.hConn

连接句柄

## rasconnstatusObject 成员列表

### rasconnstatusObject.deviceName

设备�?
### rasconnstatusObject.deviceType

设备类型

### rasconnstatusObject.err

错误代码

### rasconnstatusObject.phoneNumber

连接号码

### rasconnstatusObject.state

_RASCS_ 前缀常量表示连接状�?
### 自动完成常量

\_ET\_None=0

\_ET\_Optional=3

\_ET\_Require=1

\_ET\_RequireMax=2

\_RASCM\_DDMPreSharedKey=0x40

\_RASCM\_DefaultCreds=8

\_RASCM\_Domain=4

\_RASCM\_Password=2

\_RASCM\_PreSharedKey=0x10

\_RASCM\_ServerPreSharedKey=0x20

\_RASCM\_UserName=1

\_RASCS\_AllDevicesConnected=4

\_RASCS\_ApplySettings=0x18

\_RASCS\_AuthAck=0xC

\_RASCS\_AuthCallback=8

\_RASCS\_AuthChangePassword=9

\_RASCS\_AuthLinkSpeed=0xB

\_RASCS\_AuthNotify=6

\_RASCS\_AuthProject=0xA

\_RASCS\_AuthRetry=7

\_RASCS\_Authenticate=5

\_RASCS\_Authenticated=0xE

\_RASCS\_CallbackComplete=0x14

\_RASCS\_CallbackSetByCaller=0x1002

\_RASCS\_ConnectDevice=2

\_RASCS\_Connected=0x2000

\_RASCS\_DONE=0x2000

\_RASCS\_DeviceConnected=3

\_RASCS\_Disconnected=0x2001

\_RASCS\_Interactive=0x1000

\_RASCS\_InvokeEapUI=0x1004

\_RASCS\_LogonNetwork=0x15

\_RASCS\_OpenPort=0

\_RASCS\_PAUSED=0x1000

\_RASCS\_PasswordExpired=0x1003

\_RASCS\_PortOpened=1

\_RASCS\_PrepareForCallback=0xF

\_RASCS\_Projected=0x12

\_RASCS\_ReAuthenticate=0xD

\_RASCS\_RetryAuthentication=0x1001

\_RASCS\_StartAuthentication=0x13

\_RASCS\_SubEntryConnected=0x16

\_RASCS\_SubEntryDisconnected=0x17

\_RASCS\_WaitForCallback=0x11

\_RASCS\_WaitForModemReset=0x10

\_RASEO2\_CacheCredentials=0x2000000

\_RASEO2\_DisableIKENameEkuCheck=0x20000

\_RASEO2\_DisableNbtOverIP=0x40

\_RASEO2\_DontNegotiateMultilink=4

\_RASEO2\_DontUseRasCredentials=8

\_RASEO2\_IPv4ExplicitMetric=0x8000

\_RASEO2\_IPv6ExplicitMetric=0x10000

\_RASEO2\_IPv6RemoteDefaultGateway=0x1000

\_RASEO2\_IPv6SpecificNameServer=0x800

\_RASEO2\_Internet=0x20

\_RASEO2\_ReconnectIfDropped=0x100

\_RASEO2\_RegisterIpWithDNS=0x2000

\_RASEO2\_SecureClientForMSNet=2

\_RASEO2\_SecureFileAndPrint=1

\_RASEO2\_SecureRoutingCompartment=0x400

\_RASEO2\_SharePhoneNumbers=0x200

\_RASEO2\_UseDNSSuffixForRegistration=0x4000

\_RASEO2\_UseGlobalDeviceSettings=0x80

\_RASEO2\_UsePreSharedKey=0x10

\_RASEO\_Custom=0x100000

\_RASEO\_CustomScript=0x80000000

\_RASEO\_DisableLcpExtensions=0x20

\_RASEO\_IpHeaderCompression=8

\_RASEO\_ModemLights=0x100

\_RASEO\_NetworkLogon=0x2000

\_RASEO\_PreviewDomain=0x2000000

\_RASEO\_PreviewPhoneNumber=0x200000

\_RASEO\_PreviewUserPw=0x1000000

\_RASEO\_PromoteAlternates=0x8000

\_RASEO\_RemoteDefaultGateway=0x10

\_RASEO\_RequireCHAP=0x8000000

\_RASEO\_RequireDataEncryption=0x1000

\_RASEO\_RequireEAP=0x20000

\_RASEO\_RequireEncryptedPw=0x400

\_RASEO\_RequireMsCHAP=0x10000000

\_RASEO\_RequireMsCHAP2=0x20000000

\_RASEO\_RequireMsEncryptedPw=0x800

\_RASEO\_RequirePAP=0x40000

\_RASEO\_RequireSPAP=0x80000

\_RASEO\_RequireW95MSCHAP=0x40000000

\_RASEO\_SecureLocalFiles=0x10000

\_RASEO\_SharedPhoneNumbers=0x800000

\_RASEO\_ShowDialingProgress=0x4000000

\_RASEO\_SpecificIpAddr=2

\_RASEO\_SpecificNameServers=4

\_RASEO\_SwCompression=0x200

\_RASEO\_TerminalAfterDial=0x80

\_RASEO\_TerminalBeforeDial=0x40

\_RASEO\_UseCountryAndAreaCodes=1

\_RASEO\_UseLogonCredentials=0x4000

\_RASET\_Broadband=5

\_RASET\_Phone=1

\_RASET\_Vpn=2

\_RASFP\_Ppp=1

\_RASFP\_Ras=4

\_RASFP\_Slip=2

\_RASNP\_Ip=4

\_RASNP\_Ipv6=8

\_RASNP\_Ipx=2

\_RASNP\_NetBEUI=1

\_VS\_Default=0

\_VS\_L2tpFirst=4

\_VS\_L2tpOnly=3

\_VS\_PptpFirst=2

\_VS\_PptpOnly=1

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/inet/ras.md)

