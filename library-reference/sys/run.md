[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# sys.run 库模块帮助文�?
## sys 成员列表

### sys.run

用于为当前用户注册开机启动项，以普通权限启动，

如果希望以管理权限启动且不出现警告窗口，请改�?sys.runAsTask

建议大家不要滥用此功能，

用户未在设置中主动设置开机启动，请不要自动添加，

仅为当前用户添加开机启动，任何时候都不建议设置所有用户开机启动项�?
滥用自动开机只会招致用户反感，或被安全软件清除

### sys.run()

[返回对象:SysRunObject](#SysRunObject)

### sys.run(taskName)

创建注册与删除开机启动项工具

可选用 @taskName 参数指定启动项名称，不指定则为当前文件名

## SysRunObject 成员列表

### SysRunObject.delete()

删除开机启动项

在开发环境中此函数不执行操作，仅发布后会生效

### SysRunObject.register

添加开机启动项

在开发环境中此函数不执行操作，仅发布后会生效

### SysRunObject.register(arguments,path,workDir)

添加开机启动项

可选用 @arguments 参数指定启动参数，此参数必须是字符串�?
可选用 @path 参数指定要启动的应用程序路径,省略则为当前应用程序路径

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/sys/run.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/sys/run.md')

