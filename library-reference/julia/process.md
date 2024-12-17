[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# julia.process 库模块帮助文�?
## julia 成员列表

### julia.process()

创建 Julia 进程，打开控制台窗口�?
返回进程�?process ）对象�?
可以用一个字符串参数指定多个启动参数，用空格分隔多个参数�?
也可以传入多个参数由 aardio 自动合并（空格分隔参数）�?
合并多参数时，单参数含空格或需转义时自动加双引号并自动转义

[返回对象:processObject](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/process/_.html  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/process/_.html#processObject')

## julia.process 成员列表

### julia.process.eval()

创建 Julia 进程执行参数指定�?Julia 代码�?
不打开控制台窗口，返回进程所有输出以及表达式的值�?
主进程退出时此函数创建的 Julia 进程会自动退出�?
也可以传入多个参数由 aardio 自动合并（空格分隔参数）�?
合并多参数时，单参数含空格或需转义时自动加双引号并自动转义�?
�?Julia 代码中可以用 ARGS 获取参数

### julia.process.exec()

创建 Julia 进程执行参数指定�?Julia 代码�?
打开新的控制台窗口。返回进程（ process ）对象�?
也可以传入多个参数由 aardio 自动合并（空格分隔参数）�?
合并多参数时，单参数含空格或需转义时自动加双引号并自动转义�?
�?Julia 代码中可以用 ARGS 获取参数

[返回对象:processObject](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/process/_.html  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/process/_.html#processObject')

### julia.process.popen()

创建 Julia 进程，不打开控制台窗口�?
返回进程管道�?process.popen ）对象�?
主进程退出时此函数创建的 Julia 进程会自动退出�?
可以用一个字符串参数指定多个启动参数，用空格分隔多个参数�?
也可以传入多个参数由 aardio 自动合并（空格分隔参数）�?
合并多参数时，单参数含空格或需转义时自动加双引号并自动转义

[返回对象:processPopenObject](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/process/popen.html  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/process/popen.html#processPopenObject')

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/julia/process.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/julia/process.md')

