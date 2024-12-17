[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: JSON-RPC

```aardio aardio
//JSON-RPC
import win.ui;
/*DSG{{*/
var winform = win.form(text="JSON-RPC";right=759;bottom=469)
winform.add(
edit={cls="edit";left=13;top=18;right=734;bottom=444;edge=1;multiline=1;z=1}
)
/*}}*/

import process.python;

//启动 JSON-RPC，参数可以是 Python 代码，Python 文件路径，或 Python 模块名称
var py = process.python.jsonRpc(`

#定义允许客户端调用的�?class MyTarget(object):

    def greet(self, name):
        return "Hi, %s!" % name

    def add(self, a,b):
        return a + b

#启动 JSON-RPC 服务�?from jsonrpyc import RPC;
RPC( MyTarget() )
`);

//调用 Python 进程提供的函�?var rep,err = py.greet("Jacen")

if( rep[["result"]] ){
    winform.edit.print( `调用 py.greet("Jacen") 成功，返回值：`, rep.result )
}
else{
    /*
    本地错误�?err 为错误信息，
    服务端错误则 err �?rep[["error"]] 对象�?JSON 文本格式
    */
    winform.edit.print(  err )
}

//可以写简单一些，例如
var ret = py.add(1,2)[["result"]];
winform.edit.print(`调用 py.add(1,2) 成功，返回值：`,ret)

//允许使用命名参数
py.rpc.kwargs = true;

/*
命名参数必须写在最前面�?第一个出现的位置参数对应服务端函数的第一个位置参数�?同一个参数不能既指定命名参数，又指定位置参数�?*/
var ret = py.add(b=123,2)[["result"]];
winform.edit.print(`调用 py.add(1,2) 成功，返回值：`,ret)

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python AnyVersion/json-rpc.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python AnyVersion/json-rpc.md')

