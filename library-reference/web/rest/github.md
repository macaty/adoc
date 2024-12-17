[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# web.rest.github 库模块帮助文�?
## web.rest.github 成员列表

### web.rest.github.getContent(用户�?仓库�?文件路径,分支�?

自指定的 GitHub 网址获取数据,分支名可省略

### web.rest.github.getContent(网址)

自指定的 GitHub 网址获取数据,

包含 blob,raw �?GitHub 网址可省略域名部�?
### web.rest.github.import(网址)

自指定的 GitHub 网址获取 \*.aardio 扩展库文件代码并安装,

包含 blob,raw �?GitHub 网址可省略域名部�?

仅支持小型单文件扩展�?

项目中的文件路径必须与库目录下的子路径一�?
### web.rest.github.latestRelease("用户�?仓库�?)

获取最新发布版本信�?
如果参数@2指定文件�?或获取文件名的函�?

则返回该文件的完整下载地址

## web.rest 成员列表

### web.rest.github()

创建 GitHub 接口客户�?
使用 api 函数返回接口对象,不需要输入接口地址,

[返回对象:webRestClientObject](client.html#webRestClientObject)

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/web/rest/github.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/web/rest/github.md')

