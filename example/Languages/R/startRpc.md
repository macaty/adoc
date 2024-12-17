[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 R 语言函数

```aardio aardio
//aardio 调用 R 语言函数
import console.int;
import process.r;

//R 语言代码
var rCode = /*
add <- function(a,b,list) {

   # 转换列表为向�?   num_vec <- as.numeric(list)

   # 类似 aardio 中的 return a * b
   result <- a + num_vec[3]

   # 指定返回值以后，还能继续执行后面的代码，不像 aardio 函数 return 后面的代码被忽略�?   print(result)  # print 输出带格式，cat 输出不带格式
}
*/

//启动 R
var r = process.r.startRpc(rCode);

//调用 R 函数
var ret  = r.add(2,3,{7,8,9})

/*
ret 是符�?JSON RPC 2.0 协议的返回值对象，
ret 为任何值（包括 null），直接下标[[]]都不会报错而是返回 null
*/
ret = ret[["result"]];

//打印 R 函数返回�?console.log("R 函数返回�?,ret)

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/R/startRpc.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/R/startRpc.md')

