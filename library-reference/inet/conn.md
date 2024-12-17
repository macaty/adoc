[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# inet.conn 库模块帮助文�?
## inet.conn 成员列表

### inet.conn.setProxy

为指定连接设置代�?
如果要设置拔号连接代理，请使�?inet.ras.setProxy 函数

设置进程内代理请使用 inet.setProxy 函数

### inet.conn.setProxy("连接�?)

指定连接不使用代�?
### inet.conn.setProxy("连接�?,"SOCKS=代理服务器地址:端口","绕过代理地址")

省略连接名表示默认连�?

设置SOCKS4代理服务�?不支持登�?
绕过代理地址可在域名或IP中使用通配�?多个以分号分�?
### inet.conn.setProxy("连接�?,"代理服务器地址:端口","绕过代理地址")

省略连接名表示默认连�?

设置所有协议走 HTTP 代理服务器，

└── 指定 SOCKS 代理格式�?socks=代理服务器地址:端口"

└── [代理格式说明](../../library-guide/std/inet/proxy.html)

绕过代理地址已自动设置，建议省略保持默认即可�?
### inet.conn.setProxy()

默认连接不使用代�?
### inet.conn.setProxyAutoConfig("连接�?, "HTTP://主机地址:端口�?)

为指定连接设置自动配置代理（PAC）地址�?
省略连接名表示默认连�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/inet/conn.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/inet/conn.md')

