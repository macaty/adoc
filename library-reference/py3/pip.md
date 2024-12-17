[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# py3.pip 库模块帮助文�?
参考文�?
[https://pip.pypa.io/en/stable/cli/pip\_install/](javascript:if(confirm('https://pip.pypa.io/en/stable/cli/pip_install/  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ����һ������·���ⲿ������Ϊ������ʼ��ַ�ĵ�ַ��  \n\n�����ڷ������ϴ�����?'))window.location='https://pip.pypa.io/en/stable/cli/pip_install/')

## py3 成员列表

### py3.pip("install","字符串参�?)

执行 pip 命令，只能在开发环境单独运行�?
可以用一个字符串参数指定多个 pip 参数，用空格分格多个参数�?
也可以传入多个参数由 aardio 自动合并（空格分格参数）�?
合并多参数时，单参数含空格或需转义时自动加双引号并自动转义�?
也可以将多个字符串参数放到一个数组里作为调用参数�?
默认安装模块�?"/py/Python+版本�?site-packages" 目录�?
如果不指定任何参数，直接返回 pip 模块对象

### py3.pip()

[返回对象:py3ModuleObject](#py3ModuleObject)

## py3.pip 成员列表

aardio 自带绿色�?Python 模块安装工具�?
只能在开发环境中使用�?
导入 py3,py3.10 扩展库后可用�?
其他 Python 环境版本低于 3.7 的扩展库不可用�?
注意只能在导入库时写 py3.10.pip 这种带版本号的库�?
在调用时不能写为 py3.10.pip，应始终写为 py3.pip

个别模块在安装时调用 python.exe 会导致错误打开 aardio.exe�?
这些模块建议改用 process.python.pip 安装同版本的模块�?
然后复制�?py/site-packages 目录下就可以�?
### py3.pip.process("install","字符串参�?)

执行 pip 命令，只能在开发环境单独运行�?
可用一个字符串参数指定多个 pip 参数，空格分隔多个参数，

也可以传入多个参数由 aardio 自动合并（空格分隔参数）�?
合并多参数时，单参数含空格或需转义时自动加双引号并自动转义�?
默认安装模块�?"/py/Python+版本�?site-packages" 目录�?
### py3.pip.setIndexUrl("aliyun")

设置镜像源�?
参数指定源网址，支持常用镜像源缩写�?
"aliyun" 表示阿里云源�?
"tsinghua" 表示清化源，

"tencent" 表示腾讯源，

"douban" 表示豆瓣�?
### py3.pip.upgrade()

更新 pip

## py3.pip.process 成员列表

进程�?Python 模块安装工具�?
调用相同版本 python.exe 安装模块�?
适用于安装时会调�?python.exe 创建子进程的 Python 模块�?
避免�?py3.pip 安装模块时重复打开 aardio.exe 且安装失�?
### py3.pip.process.require("字符串参�?)

如果没有安装指定的模块，则调�?pip 安装

### py3.pip.process.setIndexUrl("aliyun")

设置镜像源�?
参数指定源网址，支持常用镜像源缩写�?
"aliyun" 表示阿里云源�?
"tsinghua" 表示清化源，

"tencent" 表示腾讯源，

"douban" 表示豆瓣�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/py3/pip.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/py3/pip.md')

