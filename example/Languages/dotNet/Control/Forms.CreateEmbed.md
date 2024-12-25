[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 嵌入 .NET 数据表格

```aardio aardio
//aardio 嵌入 .NET 数据表格
import win.ui;
/*DSG{{*/
var winform = win.form(text="嵌入 .NET 控件";right=759;bottom=510)
winform.add(
button={cls="button";text="读取数据";left=495;top=439;right=739;bottom=504;color=14120960;db=1;dr=1;font=LOGFONT(h=-14);note="获取数据源中的数�?;z=3};
custom={cls="custom";left=25;top=25;right=736;bottom=274;db=1;dl=1;dr=1;dt=1;z=1};
edit={cls="edit";left=26;top=290;right=737;bottom=435;autohscroll=false;db=1;dl=1;dr=1;edge=1;multiline=1;vscroll=1;z=2}
)
/*}}*/

import System;
import System.Data;
import System.Windows.Forms;

//.NET 控件必须�?System.Windows.Forms.CreateEmbed 嵌入 aardio 窗口
var dataGridView = System.Windows.Forms.CreateEmbed("DataGridView",winform.custom);
dataGridView.EditMode = 2;

//添加数据�?var dataTable = System.Data.DataTable("DT");
dataTable.Columns.Add("名称");//添加�?dataTable.Columns.Add("计数",System.Double); //添加指定数据类型的列
dataTable.Columns.Add("选择",System.Boolean); //自动显示复选框

//绑定数据源到视图
var dataView = System.Data.DataView(dataTable);
dataGridView.DataSource = dataView;

//替换名字�?名称"的列为下拉框控件（参�?System.Windows.Forms 库源码）
dataGridView.ReplaceNameValueListColumn("名称",120/*宽度*/,
    { "王五","张三","李四"},
    { "WangWu","ZhangSan","LiSi"}
);

//添加测试数据
var row = dataTable.NewRow();
row.ItemArray = {"WangWu",123, true}
dataTable.Rows.Add(row);

/*
可以�?FillFromArray 函数一次性填充数据�?避免密集调用 .NET 参数，减少不必要的跨语言交互成本。FillFromArray 实现请查�?System.Data.DataTable 源码�?*/
dataTable.FillFromArray({
    {"ZhangSan",456,false};
    {"LiSi",789,true}
})

//添加事件(event)
dataTable.ColumnChanged = function(sender,eventArgs){
    var columnName = eventArgs.Column.ColumnName;
    var value  = eventArgs.Row.getItem(columnName);
    winform.edit.print("已改变列�?,columnName," 已变更值：",value);
}

//读取数据
winform.button.oncommand = function(id,event){

    //一次读取所有数据到 aardio 数组
    var data = dataTable.ExtractToArray();

    //输出结果
    for(i=1;#data;1){
        winform.edit.dump(  data[i]  )
    }

    //修改数据
    data[1][2]= 999;

    //替换并更新原来的数据
    dataTable.FillFromArray(data,true)

    //下面是原始的方法，交互次数多一�?    /*
    for(i=1;dataTable.Rows.Count;1){
        var arr = dataTable.Rows[i].ItemArray;
        winform.edit.print( arr[1] )    ;
    }
    */
}

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/Control/Forms.CreateEmbed.md)

