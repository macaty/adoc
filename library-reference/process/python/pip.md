[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# process.python.pip 库模块帮助文�?
## process.python.pip 成员列表

Python 模块安装工具�?
如果 process.python.path 的值为 "python.exe" 则调用系统安装的 pip�?
否则自动安装 pip �?python.exe 所在目录的 pip 目录�?请不要改为其他名称�?
在安�?pip 时会修改 python.exe 所在目录的 \*.\_pth 文件�?
如果已安�?pip 则自动跳过�?
此工具可用于发布后的程序

### process.python.pip.github("字符串参�?)

自动安装 GitHub �?Python 项目依赖模块�?
参数中指�?GitHub �?Python 项目 requirements.txt 地址�?
如果网址包含 blob �?raw 则不用指定域�?
### process.python.pip.require("字符串参�?)

如果没有安装指定的模块，则调�?pip 安装

### process.python.pip.setIndexUrl("aliyun")

设置镜像源�?
参数指定源网址，支持常用镜像源缩写�?
"aliyun" 表示阿里云源�?
"tsinghua" 表示清化源，

"tencent" 表示腾讯源，

"douban" 表示豆瓣源，

参数为空恢复默认�?
### process.python.pip.target

指定安装模块的目录，

此目录仅用于安装，不会被添加�?process.python 的模块搜索路�?
## process.python 成员列表

### process.python.pip("install","字符串参�?)

执行 pip 命令，只能在开发环境单独运行�?
可用一个字符串参数指定多个 pip 参数，空格分隔多个参数，

也可以传入多个参数由 aardio 自动合并（空格分隔参数）�?
合并多参数时，单参数含空格或需转义时自动加双引号并自动转义�?
默认安装模块�?"/py/site-packages" 目录�?
如果不指定任何参数，直接返回 pip 模块对象�?
可用一个字符串数组指定 pip.main 函数的启动参�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/process/python/pip.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/process/python/pip.md')

