[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# web.sciter.archive 库模块帮助文�?
说明

这是「扩展库而不是修改库」的一个演示�?实现这个扩展库并不需要改动或影响原来�?web.sciter �?
这个包格式确实很适合一些不支持自动打包的编程语言�?但这种格式没有加密的作用，公共工具打包，公共 API 提取资源，明文释放到内存�?如果真的很介意别人看界面 HTML 这种事，那么这个库可以作为心理安慰剂使用�?
一般桌面软件的界面资源不会加密，很多软件是直接扔到硬盘�?Sciter 也只是用来做界面，不�?Eletron 的程序也是用 JavaScript 实现�?所以提�?Sciter �?HTML 资源基本是无意义的�?
aardio 已经有自动打包资源文件的功能，不需要多写任何代码，不需要任何多余的操作�?一般没有必要使用这�?web.sciter.archive �?
## web.sciter.archive 成员列表

### web.sciter.archive.load(path,base,release)

加载 packfolder 生成的包,

参数 @path 可以是包数据,也可以是包路�?支持资源路径,

在包路径字符串前�?操作符可以编译文件到程序�?

如果使用包含操作符，则不应重复包含该文件到资源目�?

可选使�?@base 参数指定基目录，设置后将从访问路径前面自动移除基目录�?
�?@release �?true ，则此函数调用仅在发布后生效�?
## web.sciter 成员列表

### web.sciter.archive()

创建解包�?
aardio 已经有自动打包资源文件的功能，不需要多写任何代码，不需要任何多余的操作�?
一般没有必要使用这�?web.sciter.archive

[返回对象:webSciterArchiveObject](#webSciterArchiveObject)

## webSciterArchiveObject 成员列表

### webSciterArchiveObject.base

基目�?

必须以正斜杆开始并使用斜杆分隔目录

所有访问路径会移除基目�?
### webSciterArchiveObject.close()

关闭对象

### webSciterArchiveObject.get(path)

解包并返回数�?参数指定相对路径

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/web/sciter/archive.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/web/sciter/archive.md')

