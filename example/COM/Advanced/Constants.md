[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: COM 常量

```aardio aardio
//COM 常量
import console;
import com;

var conn = com.CreateObject("ADODB.Connection")

//这种方式污染名字空间，不推荐使用
var tlb = com.GetTypeInfo(conn).GetTypeLib()
var constants = tlb.ExportConstants()
table.mix(self,constants)

//测试一�?console.log( adChar );

/*
更推荐的是下面这种方式：
aardio 里任�?COM 对象都可通过属性的方式直接读取相关的常量，例如�?*/
console.log( conn.adChar );
console.log( conn.adStateFetching )

//下面这样写也是可以的,这个速度最�?当然一般可以不用这么精打细�?console.log( 129/*adChar*/)

console.pause();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/COM/Advanced/Constants.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/COM/Advanced/Constants.md')

