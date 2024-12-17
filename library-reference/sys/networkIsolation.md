[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# sys.networkIsolation 库模块帮助文�?
## sys.networkIsolation 成员列表

用于管理 UWP 应用网络隔离配置,仅适用�?WIN10�?
### sys.networkIsolation.enableLoopback(sidConfigs)

允许或禁用指定APP容器是否可以访问本机网络

参数必须是一个表，键为SID字符串，值指定是否允许访问本机网�?

仅修改指定SID的配�?

成功返回true,失败返回false,错误信息

### sys.networkIsolation.exempt(nameOrSid,disabled)

允许或禁用指定APP容器是否可以访问本机网络

@nameOrSid参数指定应用容器名或SID,

可选参数@disabled指定是否禁用访问本机网络,

成功返回true,失败返回false,错误信息,

如果无需修改直接返回true,

否则进程不是以管理权限启动时会失败并返回false

### sys.networkIsolation.exemptAs(nameOrSid,disabled)

以管理权限允许或禁用指定APP容器是否可以访问本机网络

@nameOrSid参数指定应用容器名或SID,

可选参数@disabled指定是否禁用访问本机网络,

成功返回true,失败返回false,错误信息,

如果无需修改直接返回true,

### sys.networkIsolation.getAppContainerByName(name)

使用容器名查找并返回容器信息

### sys.networkIsolation.getAppContainerConfig()

获取所有APP容器的本机网络配�?

返回值是一个数组，数组无素请查看此函数源码

### sys.networkIsolation.getAppContainers()

返回包含所有APP容器信息的数�?
### sys.networkIsolation.getLoopbackState()

获取所有APP容器的本机网络配�?

返回值是一个表，键为SID字符串，值指定是否允许访问本机网�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/sys/networkIsolation.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/sys/networkIsolation.md')

