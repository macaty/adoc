[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 捕获 Python 标准输出

```aardio aardio
//aardio 捕获 Python 标准输出
import win.dlg.message;
import py3;

var pyCode = /**
import sys

#写个输出信息的类
class CatchOutErr:
    def __init__(self):
        self.value = ''
    def write(self, txt):
        self.value += txt

#创建有输出功能的对象
catchOutErr = CatchOutErr()

#标准输出重定向到 catchOutErr (不再输出到默认的『控制台命令行黑窗口�?
sys.stdout = catchOutErr

#标准错误输出重定向到 catchOutErr(不再输出到默认的『控制台命令行黑窗口�?
sys.stderr = catchOutErr
**/
py3.exec( pyCode )

/*
看不�?Python 代码怎么办？建议�?Python 教程，前面的范例就有链接�?不懂什么是『标准输出』怎么办？aardio 文档、Python 文档都有解释�?不懂什么是『重定向』怎么办？aardio 文档、Python 文档都有解释�?也不能每�?aardio 范例都塞一本书进来�?*/

//执行 Python 代码
py3.exec("print(1+123)");

//获取 Python 中的属性�?var pyStdoutStr = tostring(  py3.main.catchOutErr.value );

win.dlg.message().doModal(
    "Python �?print 语句输出了：" + tostring(pyStdoutStr),false
);

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python 3.x/catchOutErr.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python 3.x/catchOutErr.md')

