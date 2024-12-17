[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: Excel - 带参数属�?
```aardio aardio
//Excel - 带参数属�?import console;
import com.excel;

console.showLoading(" 正在启动 Excel ");
var excel,err = com.excel();
assert(excel,err);

excel.alerts = false;
/*
excel.Visible = true;//显示 Excel 界面
excel.alerts = true;//允许界面提示与屏幕更�?*/
var book = excel.WorkBooks.Add();
var sheet = excel.ActiveWorkbook.Sheets(1);
var cell = sheet.Cells(1,1);

cell.Value2 = "haha";  //Value2是不带参数的属�?
/*
cell.Value 是带参数的属性，
�?VB代码 可以这样赋�?cell.Value(xlRangeValueDefault) = "�?

很多 COM 控件的范例用的是 VB 代码�?aardio 用户看到可能很困惑，为什么可以对函数返回值赋值呢�?其实这是 VB 的一个语法糖，他内部会转换为类似这样的代码：
cell.setValue(xlRangeValueDefault,"�?)

而上面的(xlRangeValueDefault)是可省略的可选参数，
所�?VB 也可以写�?cell.Value = "�?

这会�?aardio 用户误以为他是无参数的属性�?如果你在 aardio 中写 cell.Value = "�?
实际会转换为 cell.setValue("�?") 当然会报参数错误�?
参�? https://docs.microsoft.com/en-us/office/vba/api/excel.range.value
*/

//aardio 写带参数的属性，需要加�?set 前缀�?cell.setValue(excel.xlRangeValueDefault,"�?)
cell.setValue(,"�?") //aardio 写带参数的属性，并省略可选参数：

//aardio 读带参数的属性，需要加�?get 前缀�?console.log( cell.getValue(excel.xlRangeValueMSPersistXML) )
console.log( cell.getValue() ) //这个参数可省�?console.log( cell.Value ) //这样�?aardio 会转换为 cell.getValue()
/*
aardio 访问 COM 对象成员的规则是这样�?-------------------------------------------
comObject.Value 解析为读写COM对象属性�?comObject.getValue() 找到对象名称�?Value 的属性并将其作为读属性函数调用�?comObject.setValue() 找到对象名称�?Value 的属性并将其作为读属性函数调用�?comObject.Value() 找到对象名称�?Value 的成员并将其作为函数调用�?
comObject.Value = v 会转换为 comObject.setValue(v)
var v = comObject.Value  会转换为 var v = comObject.getValue()

访问 COM 对象的成员最终都会转换为函数调用�?如果�?aardio 代码中写 comObject.Value() 那么 comObject.Value 一定是函数�?但省略调用操作符() 写为comObject.Value 就是访问 COM 对象属性了�?
并不是所有COM对象属性都要带�?set,get 前缀去访问�?很明显无参数的属性不需要加前缀�?
带参数的属性，如果是只读的属性通常也不需要加前缀�?例如上面代码中的 var cell = sheet.Cells(1,1);
也可以写�?var cell = sheet.getCells(1,1);
但没必要这么写，因为这是一个只读的属性，对方不会混淆你的意图�?
但如果你�? cell.Value()
Excel 就懵了，你觉得你是要读属性，�?Excel 误以为你是要把单元格的值清空�?*/

excel.Quit();
console.pause();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/COM/Excel/property.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/COM/Excel/property.md')

