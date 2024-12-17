[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# sys.tpmInfo 库模块帮助文�?
## sys.tpmInfo 成员列表

用于获取可信平台模块（Trusted Platform Module）支持信�?
### sys.tpmInfo.get()

返回 TPM 信息,

不支�?TPM 返回 null,

[返回对象:sysTpmInfoObject](#sysTpmInfoObject)

## sysTpmInfoObject 成员列表

### sysTpmInfoObject.activated

是否激�?
### sysTpmInfoObject.enabled

是否启用

### sysTpmInfoObject.version

支持版本,

多个版本以逗号分开,

如果进程无管理权限仅返回当前版本�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/sys/tpmInfo.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/sys/tpmInfo.md')

