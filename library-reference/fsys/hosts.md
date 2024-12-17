[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# fsys.hosts 库模块帮助文�?
## fsys.hosts 成员列表

### fsys.hosts.flushDns()

清空DNSxe

### fsys.hosts.load()

自host文件中读取一个表，每个键值对表示一个域名对应的IP

### fsys.hosts.loadText()

自host文件直接读取文本内容

### fsys.hosts.ownCacls()

获取host文件的控制权限，

当前进程需要以管理权限启动

### fsys.hosts.path

HOSTS文件路径

### fsys.hosts.saveText()

将参数指定的文本保存到host文件

### fsys.hosts.update(hostSetting)

```aardio aardio
fsys.hosts.update(
    [/*在这里指定要在host中修改IP的域�?/] = "127.0.0.1";
)

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/fsys/hosts.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/fsys/hosts.md')

