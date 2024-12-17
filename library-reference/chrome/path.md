[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# chrome.path 库模块帮助文�?
## chrome 成员列表

### chrome.path(允许自动安装,优先查找Chrome)

用于获取 Chrome 安装路径，所有参数可省略�?
支持 Chrome �?Edge（Chromium ）、Supermium 等浏览器

如果允许自动安装，且没有可用浏览�?，将会下载安�?Edge（Chromium�?
默认优先获取 Edge（Chromium）路径，如参�?@2 �?true 则优先获�?Chrome 路径

Win10 以后系统自带 Edge（Chromium ）一般不需要安装�?
如果允许自动安装，则 Win10 以后安装 Edge（Chromium ）�?
Win7 安装 Chrome 109，XP 安装 Chrome 49

## chrome.path 成员列表

用于获取 Edge（Chromium ）、Chrome �?Supermium 安装路径

### chrome.path.profile(profile,path,userDataDir)

获取 Edget �?Chrome 用户配置文件（Profile）所在目录�?
所有参数可选：

@profile 指定配置目录名�?
@path 批定子路径�?
@userDataDir 指定用户数据根目录�?
如果返回的文件路径（拼接 @path 以后）不存在则返�?null �?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/chrome/path.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/chrome/path.md')

