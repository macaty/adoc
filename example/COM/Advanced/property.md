[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: COM 接口 - 带参数属�?
```aardio aardio
//COM 接口 - 带参数属�?import console;
import com.excel;

console.showLoading(" 正在启动 Excel ");
var excel,err = com.excel();
assert(excel,err);

excel.alerts = false;
var book = excel.WorkBooks.Add();
var sheet = excel.ActiveWorkbook.Sheets(1);
var cell = sheet.Cells(1,1);

cell.Value2 = "haha";  //Value2是不带参数的属�?
/*
cell.Value 是带参数的属性，
加上 set 前缀可以指定所有属性参数�?*/
cell.setValue(excel.xlRangeValueDefault,"�?)
cell.setValue(,"�?") //省略可选参�?cell.setValue("�?") //写属性值时，可直接略写其他可选参数�?cell.value = "�?" //这样写也可以

//aardio 读带参数的属性，需要加�?get 前缀�?console.log( cell.getValue(excel.xlRangeValueMSPersistXML) )
console.log( cell.getValue() ) //这个参数可省�?console.log( cell.Value() ) //这样写也可以
/*
aardio 访问 COM 对象成员的规则是这样�?-------------------------------------------
comObject.value 解析为读�?COM 对象属性�?comObject.Value() 这样写一定会返回函数对象，然后调用该函数�?comObject.getValue() 找到对象名称�?Value 的属性并将其作为读属性函数调用�?comObject.setValue() 找到对象名称�?Value 的属性并将其作为写属性函数调用�?
comObject.Value = v 会转换为 comObject.setValue(v)
var v = comObject.Value  会转换为 var v = comObject.getValue()

访问 COM 对象的成员最终都会转换为函数调用�?如果�?aardio 代码中写 comObject.value() 那么 comObject.value 一定是函数�?但省略调用操作符() 写为comObject.value 就是访问 COM 对象属性了�?有些接口会区分这两种写法，有的不会区分�?
并不是所�?COM 对象属性都要带�?set,get 前缀去访问�?大多时候都不需要加前缀，无参数的属性基本都不需要加前缀�?带参数属性但参数是可选的，这也不需要加 set,get 前缀�?
只读的属性通常也不需要加前缀�?例如上面代码中的 var cell = sheet.Cells(1,1);
因为这是一个只读的属性，对方不会混淆你的意图�?*/

excel.Quit();
console.pause();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/COM/Advanced/property.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/COM/Advanced/property.md')

