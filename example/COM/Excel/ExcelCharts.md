[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: Excel 图表

```aardio aardio
//Excel 图表
import com.excel;

var excel,err = com.excel( true );
assert(excel,err);

var book  = excel.WorkBooks.Add();
var sheet = book.Worksheets(1);
excel.Visible = true; //显示 Excel 界面

for row=1;30 {
  sheet.Cells(row, 1).Value2 = math.floor(math.random(1*19) * 100)
}

var chart = excel.Charts.Add();
chart.ChartType = 4; //xlLine

var range = sheet.Range("A1:A30");
chart.SetSourceData(range,2);

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/COM/Excel/ExcelCharts.md)

