[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# inet.stat 库模块帮助文�?
## inet 成员列表

### inet.stat()

返回网络连接状态列�?
可选在参数中指定端口号,例如列出IIS的连接参数可指定�?0

返回对象的tcp/udp成员包含所有tcp/udp连接的数�?
返回的TCP连接会按远程IP的连接数排序

每个连接的字段含义：

remote 源IP

local 目标IP

remotePort 源端�?
localPort 目标端口

pid 进程ID

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/inet/stat.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/inet/stat.md')

