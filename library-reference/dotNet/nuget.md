[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# dotNet.nuget 库模块帮助文�?
## dotNet.nuget 成员列表

NuGet 接口操作

### dotNet.nuget.download

下载 NuGet �?
### dotNet.nuget.download(package,version,downDir,extraDir,ownerForm)

下载 NuGet 包。\\m@package 指定包名称�?
@version 指定包版本，不指定则下载最后一个版本�?
@downDir 可选参数，用于指定下载目录，默认为 /download�?
@extraDir 可选参数，用于指定解压目录�?
不指定则在下载目录根据包名自动生成解压目录�?
下载成功返回解压目录，失败返�?null

### dotNet.nuget.getPackageIndex()

返回指定 Package 的版本信息�?
成功返回表的 versions 字段为版本数组�?
失败返回 null 与错误信�?
### dotNet.nuget.http

web.rest.jsonLiteClient 客户端�?
[返回对象:webRestClientObject](../web/rest/client.html#webRestClientObject)

### dotNet.nuget.query()

搜索包�?
参数 @1 可选指定一个查询参数表�?
参数表支持的字段�?
[https://learn.microsoft.com/nuget/api/search-query-service-resource](javascript:if(confirm('https://learn.microsoft.com/nuget/api/search-query-service-resource  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ����һ������·���ⲿ������Ϊ������ʼ��ַ�ĵ�ַ��  \n\n�����ڷ������ϴ�����?'))window.location='https://learn.microsoft.com/nuget/api/search-query-service-resource')

### dotNet.nuget.service()

返回 web.rest.jsonLiteClient 引入�?API 对象,

参数指定 NuGet 服务名，省略参数则默认为 "PackageBaseAddress/3.0.0"

[返回对象:webRestApiObject](../web/rest/client.html#webRestApiObject)

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/dotNet/nuget.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/dotNet/nuget.md')

