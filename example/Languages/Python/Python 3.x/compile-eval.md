[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 eval 计算 Python 表达式�?
```aardio aardio
//aardio 调用 eval 计算 Python 表达式�?import console;
import py3;

//编译python代码对象
var code =  py3.compile("1+2");

//运行代码并返回�?console.log( code.eval() )

var dict = py3.dict() //创建一个自定义的名字空�?dict.exec("x=123"); //在名字空间下执行代码
console.log( dict.eval("x")   ) //在自定义的名字空间下执行eval功能

console.pause()

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python 3.x/compile-eval.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python 3.x/compile-eval.md')

