[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 执行 Python 代码

```aardio aardio
//aardio 执行 Python 代码
import console.int;
import py3;

py3.main.testData = "可以这样预先指定 Python 全局变量";

//Python 代码，注�?Python 对空格有严格要求，乱按空格报错不�?bug�?var pyCode = /**
def getList(a,b):
    return [a,b,testData] # 返回列表
    #return a,b,testData # Python 多返回值实际是返回一�?tuple
**/

/*
执行 Python3 的代码，
如果参数 pyCode 为类�?"/res/py.aardio" 这样�?aardio 代码路径�?则支持模板语法： https://www.aardio.com/zh-cn/doc/language-reference/templating/syntax.html
*/
py3.exec( pyCode )

//�?py3.main 模块调用 Python 代码定义的函�?var pyList = py3.main.getList(12,23);

//list �?tuple 可用下标访问，Python 对象起始索引�?0，aardio 数组起始索引�?1�?var num = pyList[0];

//可以如下遍历 pyObject 对象�?for( pyItem in pyList.each() ){
    console.log(pyItem) //基础类型已转换为�?aardio 值，其他�?py2.object
}

//pyObject 支持 table.eachIndex 创建的迭代器
for i,pyItem in table.eachIndex(pyList){
    console.log( i,pyItem ) //基础类型已转换为�?aardio 值，其他�?py2.object
}

//转换为纯 aardio �?var list = pyList.parseValue()

console.dump(list);

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python 3.x/exec.md)

