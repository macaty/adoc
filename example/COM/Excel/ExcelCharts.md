[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: Excel 鍥捐〃

```aardio aardio
//Excel 鍥捐〃
import com.excel;

var excel,err = com.excel( true );
assert(excel,err);

var book  = excel.WorkBooks.Add();
var sheet = book.Worksheets(1);
excel.Visible = true; //鏄剧ず Excel 鐣岄潰

for row=1;30 {
  sheet.Cells(row, 1).Value2 = math.floor(math.random(1*19) * 100)
}

var chart = excel.Charts.Add();
chart.ChartType = 4; //xlLine

var range = sheet.Range("A1:A30");
chart.SetSourceData(range,2);

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/COM/Excel/ExcelCharts.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/COM/Excel/ExcelCharts.md')

