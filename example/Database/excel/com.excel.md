[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: COM 接口操作 Excel

```aardio aardio
//COM 接口操作 Excel
import console;
import com.excel;

console.showLoading(" 正在启动 Excel ");
var excel,err = com.excel();
assert(excel,err);

//excel.Visible = true; //使Excel窗口可见
excel.alerts = false; //关闭所有操作提�?
var book = excel.WorkBooks.Add(); //创建工作�?// book = excel.Open( "\test.xls" );

var sheet = excel.ActiveWorkbook.Sheets(1);
var cell = sheet.Cells(1,1);
cell.Value2 = "haha";

console.log( cell.Text );

//遍列所有单元格
for(i,values in excel.eachValue(1) ){
    console.log("行号"+i,table.tostring(values));
}

excel.Quit(); //退�?console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Database/excel/com.excel.md)

