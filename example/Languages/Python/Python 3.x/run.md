[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: �?aardio 中模�?Python.exe 运行

```aardio aardio
//�?aardio 中模�?Python.exe 运行

import console;
import py3;

//必须先打开控制�?console.setTitle("python(aardio)");

//如果使用 py3.10 扩展库，py3.run() 会重�?sys.path �?py3.getPath()�?py3.run();

/*
有些 Python 程序只考虑�?python.exe 环境�?运行时会重复启动 python.exe，如果是在生�?EXE 以前运行就会错误启动 aardio.exe�?这类程序建议改用 aardio 提供�?process.python 做进程外调用�?
如果一定要�?py3 扩展库这种进程内调用，可以试试在 main.aardio 中加�?if( #_ARGV && !_STUDIO_INVOKED) return py3.run( _ARGV )
然后生成 EXE 以后再运行�?*/

console.pause()

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python 3.x/run.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python 3.x/run.md')

