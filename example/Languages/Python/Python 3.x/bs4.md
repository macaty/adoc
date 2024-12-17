[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 Python 模块 bs4

```aardio aardio
//bs4
import win.ui;
/*DSG{{*/
mainForm = win.form(text="aardio 调用 Python 模块 bs4";right=959;bottom=591)
mainForm.add(
edit={cls="edit";left=285;top=18;right=931;bottom=564;db=1;dl=1;dr=1;dt=1;edge=1;hscroll=1;multiline=1;vscroll=1;z=1}
)
/*}}*/

import py3;

/*
1、要在此之前执行 import py3;
2、py3.lib.bs4 引入模块的关键代码是�?py3.appendPath("~\lib\py3\lib\bs4\.py")
3、bs4 模块不需要手动复制到发布目录�?/dist/ ）下，而是�?~\lib\py3\lib\bs4\.build\main.aardio 自动发布�?�?aardio 中路径前面的 ~ 表示启动 EXE 所在目�?*/
import py3.lib.bs4;//右键点这个库,然后点「跳转到定义」查看源�?
//py3.exec("/res/callpy.py") //也可以这样执行资源目录下的文�?不需要先执行 string.load() 加载文件
py3.exec(`
from urllib.request import urlopen
from urllib.error import HTTPError
from bs4 import BeautifulSoup

def getTitle(url):
    """爬虫获取网页标题"""
    try:
        html = urlopen(url)
    except HTTPError as e:
        return None

    try:
        bsObj = BeautifulSoup(html.read(), "html.parser")
        title = bsObj.head.title.string
    except AttributeError as e:
        return None
    return title
`);

var pyStr = py3.main.getTitle("https://www.aardio.com" );

mainForm.edit.print( pyStr );

mainForm.show();
return win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python 3.x/bs4.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python 3.x/bs4.md')

