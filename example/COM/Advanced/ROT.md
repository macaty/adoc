[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: COM 接口 - ROT 运行对象�?
```aardio aardio
//COM 接口 - ROT 运行对象�?import console;
import com;

//枚举 ROT 对象
com.enumRunning(
    function(name,object){
        var interface = com.GetTypeInfo(object).GetDocumentation().name;
        console.log(name,interface)
        //console.dump(object)
    }
)

/*
遍历 ROT 对象�?com.eachRunning 的第一个参数可指定接口类型名称（完全匹配，返回为迭代变�?interface）�?第二个参数可指定显示名称（支持模式匹配，返回为迭代变�?name ）�?*/
for object,interface,name,i in com.eachRunning() {
    console.log(bject,interface,name)
}

console.pause(true);

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/COM/Advanced/ROT.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/COM/Advanced/ROT.md')

