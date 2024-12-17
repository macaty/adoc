[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 操作 .NET 字典（Dictionary�?
```aardio aardio
//aardio 操作 .NET 字典（Dictionary�?import dotNet;

//.NET 字典（Dictionary）是泛型类，可以像下面这样创�?Dictionary�?/*
var Dictionary = System.Collections.Generic.Dictionary.$(System.String,System.String)
var dic = Dictionary();
*/

/*
更简单的方法是使�?dotNet.dict 创建 .NET 字典（Dictionary�?�?参数 @1 指定一�?aardio 非空表，键的数据类型必须相同，值的数据类型也必须相同�?参数 @2 如果�?true 则返回对象可用于 .NET 输出引用参数，参�?@2 是可选参数�?*/
var dict = dotNet.dict(
    a="abc",
    d="789"
)

dict["a"] = "新的�?;
var v = dict["a"];

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/Advanced/dict.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/Advanced/dict.md')

