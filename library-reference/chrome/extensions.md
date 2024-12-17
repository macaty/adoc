[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# chrome.extensions 库模块帮助文�?
## chrome.extensions 成员列表

已安装的浏览器扩展�?
相关库： web.nativeMessaging, fsys.crx

### chrome.extensions.find(kw,profile)

获取 Edge �?Chrome 浏览器扩展安装信息�?
@kw 可指定系统浏览器扩展 ID、或名称、描述包含的关键字（忽略大小写）�?
@profile 指定配置，默认为 "Default"�?
### chrome.extensions.findChrome(kw,profile)

获取 Chrome 浏览器扩展安装信息�?
@kw 可指定系统浏览器扩展 ID、或名称、描述包含的关键字（忽略大小写）�?
@profile 指定配置，默认为 "Default"�?
### chrome.extensions.findEdge(kw,profile)

获取 Edge 浏览器扩展安装信息�?
@kw 可指定系统浏览器扩展 ID、或名称、描述包含的关键字（忽略大小写）�?
@profile 指定配置，默认为 "Default"�?
### chrome.extensions.get()

返回 Chrome 已安装的扩展程序数组�?
可选用参数 @2 自定�?profile，可选用参数 @2 自定义扩展所在目录�?
可用 # 操作符取数组长度判断返回结果是否为空�?
### chrome.extensions.getEdge()

返回 Edge 已安装的扩展程序数组�?
可选用参数 @2 自定�?profile，可选用参数 @2 自定义扩展所在目录�?
可用 # 操作符取数组长度判断返回结果是否为空�?
### chrome.extensions.getPath(kw,profile)

获取 Edge �?Chrome 浏览器扩展所在目录路径�?
@kw 可指定系统浏览器扩展 ID、或名称、描述包含的关键字（忽略大小写）�?
@profile 指定配置，默认为 "Default"�?
### chrome.extensions.getProfilePath(profile,path,userDataDir)

获取用户配置文件（Profile）所在目录�?
所有参数可选：

@profile 指定配置目录名�?
@path 批定子路径�?
@userDataDir 指定用户数据根目录�?
如果返回的文件路径（拼接 @path 以后）不存在则返�?null �?
### chrome.extensions.open(kw,profile)

获取 Edge �?Chrome 浏览器扩展所在目录路径并打开目录�?
@kw 可指定系统浏览器扩展 ID、或名称、描述包含的关键字（忽略大小写）�?
@profile 指定配置，默认为 "Default"�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/chrome/extensions.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/chrome/extensions.md')

