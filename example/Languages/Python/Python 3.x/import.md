[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: �?aardio 中导�?Python 模块

```aardio aardio
//�?aardio 中导�?Python 模块
import console;
import py3;

var pyCode = /**
import urllib.request
def getHtml(url):
    b = urllib.request.urlopen(url).read()
    return b.decode("utf-8")
**/

//Python 模块请放在工程目录的 /py 目录下，
string.save("/py/myHttp.py",pyCode );//创建一个自定义模块文件

/*
默认在以下两个目录搜�?Python 模块:
这两个目录都会在生成 EXE 时复制到发布目录（即�?"\py" 目录没有添加到工程中�?
    "\py"
    "~\lib\py3\.res\DLLs"

"\py" :
    文件路径开始为单个斜杠（或反斜杠）表示应用程序根目录，
    应用程序根目录在开发时指工程根目录（工程外单独启动代码则为文件所在目录）�?    发布后应用程序根目录就是�?EXE 所在的目录�?
"~\lib\py3\.res\DLLs" :

    aardio 规定文件路径开始为波浪线表�?EXE 所在的目录（开发时�?aardio.exe 所在目录）�?
可以自己添加模块搜索路径，例如：

    py3.appendPath("\py\site-packages\");
*/

//试试�?Python �?import 上面保存的测试模块（当然也可以在 Python 代码�?import�?var myHttp = py3.import("myHttp");

//如果导入模块出错，打错错误信息�?console.log( py3.lasterr() );

var str = myHttp.getHtml("http://www.aardio.com" );

import console;
console.log( str );
console.pause()

/*
aardio �?Python �?import 语句基本用法类似�?都是用来导入模块，都要求文件名与模块路径与文件路径保持一致�?
�?aardio �?import 语句更简单，
Python �?import 语句则有很多复杂的功能，例如�?
    from 模块�?import 函数�?    from 模块�?import *
    from hashlib import md5 as md5New

等等用法，并且可以任意添加修改搜索模块的路径�?
aardio 需要在 import 过来的库中用 namespace 定义名字空间，�?Python 并不需要这么做�?Python 文件放到哪里模块名字就变成什么，所以经常会�?Python 代码中看到这句代�?if __name__ == "__main__":
如果一个库被直接执�?__name__ 的值就�?"__main__",否则就是当前导入的模块名字或者当前类的名字�?
当然，复杂是有代价的，Python 的模块不但安装、部署比较麻烦，容易出现模块间的依赖与版本冲突，
在生成软件时也不容易做到按需引用、按需发布，但�?aardio 中我们可以用类似 py3.lib.numpy 这样的扩展库解决这一麻烦�?*/

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python 3.x/import.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python 3.x/import.md')
