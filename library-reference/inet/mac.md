[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# inet.mac 库模块帮助文�?
## inet.mac 成员列表

```aardio aardio
Media Access Control

```

### inet.mac.getAddress("IP或域�?,端口)

返回当前联网目标主机的网卡的MAC地址

返回�?�?OID\_802\_3\_CURRENT\_ADDRESS,

返回�?为硬件MAC,即OID\_802\_3\_PERMANENT\_ADDRESS

无法连接目标主机返回空�?
### inet.mac.getPermanentAddress("网卡ID")

返回硬件MAC - OID\_802\_3\_PERMANENT\_ADDRESS

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/inet/mac.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/inet/mac.md')

