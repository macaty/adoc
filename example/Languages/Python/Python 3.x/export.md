[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 导出 aardio 对象�?Python 模块

```aardio aardio
//导出 aardio 对象�?Python 模块
import win.ui;
/*DSG{{*/
var winform = win.form(text='导出一个名字为"aardio"的模块到 Python 代码';right=759;bottom=469)
winform.add(
button={cls="button";text="调用python显示图片";left=448;top=360;right=640;bottom=416;z=2};
plus={cls="plus";left=80;top=80;right=680;bottom=264;repeat="center";z=1}
)
/*}}*/

/*
导出一个名字为"aardio"的模块，
在python中可以使�?import aardio导入�?
可以使用此方法导出任何其他的aardio表，Python中可以访问导出表中的成员函数,
除函数以外的成员不导出，但是可以在被调用函数中用owner对象访问自身的其他成员变量�?
虽然 aardio �?Python 传值，Python �?aardio 传址
�?Python 回调 aardio 函数的回调参数会自动调用 parseValue() 解析�?aardio 值�?*/
import py3;
py3.export.aardio ={
    showImage = function(bytes){
        winform.plus.background =  bytes;
    }
}

var pyCode = /**
import aardio;
import requests;
def testPy():
    '''
    如果开全局代理，Python 可能会报错（SSLEOFError），
    这个问题�?Python 的问题与 aardio 无关，解决方案请自行上网搜索�?    也可以改�?aardio 中的 inet.http �?web.rest.client 等抓取网页�?    '''
    res = requests.get("https://aardio.com/images/logo.png",verify=True)
    aardio.showImage(res.content)
**/
py3.exec( pyCode );//运行Python代码

winform.button.oncommand = function(id,event){
    py3.main.testPy(); //调用python函数
}

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python 3.x/export.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python 3.x/export.md')

