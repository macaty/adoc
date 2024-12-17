[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# aardio 范例: ReoGrid - 免费、开源、强大的 Excel 表格控件

```aardio aardio
//表格控件
import win.ui;
/*DSG{{*/
var winform = win.form(text="ReoGrid - 免费、开源、强大的 Excel 表格控件";right=757;bottom=467)
winform.add()
/*}}*/

//免费、开源、强大的 Excel 表格控件�?//�?aardio 里用法基本跟 .NET 一样，文档: https://reogrid.net/document/
import dotNet.ReoGrid;

//创建控件
var grid = ReoGrid.ReoGridControl(winform);

//当前工作�?var sheet1 = grid.CurrentWorksheet;

//修改数据
sheet1.Cells["A1"].Data = "测试";

//直接显示 aardio 表（字符串数组）
sheet1["B2:D4"] =  {
  { "测试", "测试2" },
  { "测试3", "测试4" },
};

//设置列数据，参数（行索引、列索引，数据），注�?.NET 起始下标�?0
sheet1.SetCellData(5, 2, "hello world");

//设置列数�?sheet1["B3:C5"] =  { { 'a', 'b', 'c' }, { 1, 2, 3 }, { 4, 5, 6 } };

//获取 Range（单元格集合�?对象
var range = sheet1.Ranges["D4:I4"];

//设置 Range 数据
range.Data = { "Product", "Unit Price", "Quantity", "Extended Price" };

//修改样式（背景颜色） ，参数必须是 ReoGrid.Graphics.SolidColor 对象
range.Style.BackColor = ReoGrid.Graphics.SolidColor.Orange

//高亮区域
sheet1.AddHighlightRange("B2:D4");

///自定义控�?var checkboxCell = ReoGrid.CellTypes.CheckBoxCell();

//响应事件，不用任何封装，aardio 自动支持�?checkboxCell.CheckChanged = function(send,event){
    winform.msgbox(checkboxCell.IsChecked)
}
sheet1["B6"] = checkboxCell;

//保存文件
grid.Save("/test.xlsx");

winform.show();
win.loopMessage();

//可如下快速编�?C# 函数然后调用�?/****

import dotNet.ReoGrid.Compiler;
var compiler = dotNet.ReoGrid.Compiler();

//C# 源码
compiler.Source = /***
using System;
using unvell.ReoGrid;

namespace aardio.ReoGrid{
    public class Util
    {
        public static void TestGrid(ReoGridControl grid,string path){
            grid.Save(path);
        }
    }
}
***/

//生成程序�?compiler.CompileOrFail("/Grid.dll");

//加载 DLL，改�?$"/Grid.dll" 内存加载（不需要外�?DLL文件�?var dll = dotNet.loadFile("/Grid.dll");

//导入 C# 名字空间
var gridUtil = dll.import("aardio.ReoGrid.Util");

//调用 C# 写的函数
gridUtil.TestGrid(grid,io.fullpath("/test2.xlsx"));

****/

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Excel/ReoGrid.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Excel/ReoGrid.md')

