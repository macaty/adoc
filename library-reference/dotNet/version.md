[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# dotNet.version 库模块帮助文�?
## dotNet.version 成员列表

检�?.NET Framework 安装版本�?
检�?CLR 加载版本可参�?System.Environment 库源代码�?
### dotNet.version.getFrameworks()

获取安装�?.Net Framework 版本信息列表

可选用参数@1指定注册表版本主键匹配模式串，默认为 "^v\\d"

### dotNet.version.getVersions()

返回已安装的 .Net Framework 版本

版本号一律规范为 vN.N 格式,例如 v2.0 v4.0 等等

注意 .NET 3.5的运行时�?v2.0�?Net 4.5 的运行时�?v4.0�?
Win7 自带 .NET2.0 运行时，Win10 自带 .NET4.0 运行时�?
aardio 可以自适应不同的版本，

所以大多时候不需要去指定版本

### dotNet.version.v450PlusCheck()

是否已安装大于等�?v4.5.0 版本�?.NET Framework�?
并检查Release 版本号是否大于等于参数指定的数值�?
参数指定�?0 则只检查已安装版本是否大于等于 v4.5.0

### dotNet.version.v460Later()

是否已安装大于等�?v4.6.0 版本�?.NET Framework

### dotNet.version.v461Later()

是否已安装大于等�?v4.6.1 版本�?.NET Framework

### dotNet.version.v462Later()

是否已安装大于等�?v4.6.2 版本�?.NET Framework

### dotNet.version.v470Later()

是否已安装大于等�?v4.7.0 版本�?.NET Framework

### dotNet.version.v471Later()

是否已安装大于等�?v4.7.1 版本�?.NET Framework

### dotNet.version.v472Later()

是否已安装大于等�?v4.7.2 版本�?.NET Framework

### dotNet.version.v480Later()

是否已安装大于等�?v4.8.0 版本�?.NET Framework

### dotNet.version.v481Later()

是否已安装大于等�?v4.8.1 版本�?.NET Framework

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/dotNet/version.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/dotNet/version.md')

