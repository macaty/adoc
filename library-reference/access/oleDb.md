[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# access.oleDb 库模块帮助文�?
## access.oleDb 成员列表

导入 access.oleDb 后，

access 库可自动检测或安装支持 _.xlsx,_.accdb 等文件的 OLEDB 驱动程序�?
如果数据库连接参数未显式指定使用驱动 "Microsoft.ACE.OLEDB.16.0" �?
则默认兼容系统已安装�?"Microsoft.ACE.OLEDB.12.0" 驱动�?
如果未安装合适的驱动，则自动安装 "Microsoft.ACE.OLEDB.16.0" �?
### access.oleDb.exist()

检�?Microsoft.ACE.OLEDB.16.0 驱动程序是否已安装，

成功返回驱动�?"Microsoft.ACE.OLEDB.16.0 "�?
### access.oleDb.exist(true)

检�?Microsoft.ACE.OLEDB.16.0 驱动程序是否已安装，

成功返回驱动�?"Microsoft.ACE.OLEDB.16.0 "�?
失败则检�?Microsoft.ACE.OLEDB.12.0 驱动程序是否已安装，

成功返回驱动�?"Microsoft.ACE.OLEDB.12.0 "�?
### access.oleDb.install(父窗�?允许兼容旧组�?

所有参数可选�?
如果已安�?"Microsoft.ACE.OLEDB.16.0" 则返回该驱动名�?
如果许兼容旧组件�?true 且系统已安装 "Microsoft.ACE.OLEDB.12.0" 则返回该驱动名�?
否则自动下载并安�?Microsoft.ACE.OLEDB.16.0�?
安装成功返回驱动�?"Microsoft.ACE.OLEDB.16.0 " �?
失败返回 null �?
安装驱动程序时需要管理权限，

在已经有管理权限的安装向导中可自动执行，

普通权限进程需要用户确�?
[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/access/oleDb.md)

