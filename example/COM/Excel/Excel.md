[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: Excel 基础操作

```aardio aardio
//Excel 基础操作
import console;
import com.excel;

console.showLoading(" 正在启动 Excel ");
var excel,err = com.excel();
assert(excel,err);

excel.alerts = false; //关闭界面提示与屏幕更�?/*
excel.Visible = true;//显示 Excel 界面
excel.alerts = true;//允许界面提示与屏幕更�?excel.Application.ScreenUpdating = true;//单独设置屏幕更新
https://docs.microsoft.com/en-us/office/vba/api/excel.application%28object%29
*/

var book = excel.WorkBooks.Add(); //创建工作�?//book = excel.Open( "\test.xls" );

var sheet = excel.ActiveWorkbook.Sheets(1);
var cell = sheet.Cells(1,1);

//https://docs.microsoft.com/en-us/office/vba/api/excel.range.value2
cell.Value2 = "haha";

console.log( cell.Text );

//遍列所有单元格
for(i,values in excel.eachValue(1) ){
    console.log("行号"+i,table.tostring(values));
}

//下面两种方法都可以输入常量，_xl 前缀会触发智能提示（推荐这种�?excel.Calculation = -4105/*_xlCalculationAutomatic*/
excel.Calculation = excel.xlCalculationAutomatic;

excel.Quit(); //退�?//所有存�?Excel 创建或返回对象的变量离开作用域并被回收后才会完全退�?Excel ,可调�?collectgarbage("collect") 提前回收资源

console.pause();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/COM/Excel/Excel.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/COM/Excel/Excel.md')

