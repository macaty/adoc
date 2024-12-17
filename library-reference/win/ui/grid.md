[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# win.ui.grid 库模块帮助文�?
## win.ui 成员列表

### win.ui.grid()

参数必须指定一个listview控件对象

返回一个可编辑单元格的列表视图对象,

鼠标左键单击单元格、或者按空格键开始编�?

回车完成编辑,ESC键撤消编�?回车+上下方向键快速移动到其他�?

用户完成编辑后会触发onEditChanged事件.

[返回对象:listviewObject](ctrl/listview.html#listviewObject)

[返回对象:winUiGridObject](#winUiGridObject)

## winUiGridObject 成员列表

### winUiGridObject.beginEdit(�?�?

切换到编辑状�?
### winUiGridObject.clear()

清空所有行

### winUiGridObject.clear(true)

清空所有行,并且清空所有列

### winUiGridObject.columnCount

列总数

### winUiGridObject.delColumn()

删除指定�?
### winUiGridObject.editBox

实现编辑功能的edit控件

此功能需要扩展listview并实现了编辑功能的的控件才能支持

[返回对象:editObject](ctrl/edit.html#editObject)

### winUiGridObject.getColumnText()

取指定列文本

### winUiGridObject.getTable()

返回数据表�?
如果参数 @1 指定列名数组（被复制为返回表�?fields 字段），

则返回的每行数据都是名值对，否则返回的每行数据都是文本数组�?
如果参数 @1 �?true，则返回的文本数组第一行为列标题文本数组�?
### winUiGridObject.onCheckedChanged

```aardio aardio
winUiGridObject.onCheckedChanged = function(checked,item){
    /*勾选状态变更触发此事件�?checked 为是否勾选，item 为变更项序号*/
}

```

### winUiGridObject.onClick

```aardio aardio
winUiGridObject.onClick = functionitem,subItem,nmListView){
    /*左键单击项目触发此事件�?item 为变更为焦点的项序号，subItem 为列序号，nmListView �?NMLISTVIEW 结构�?/
}

```

### winUiGridObject.onDoubleClick

```aardio aardio
winUiGridObject.onDoubleClick = function(item,subItem,nmListView){
    /*左键双击项目触发此事件�?item 为变更为焦点的项序号，subItem 为列序号，nmListView �?NMLISTVIEW 结构�?/
}

```

### winUiGridObject.onEditChanged(text,iItem,iSubItem)

```aardio aardio
winUiGridObject.onEditChanged = function(text,iItem,iSubItem){
    /*控件完成编辑,并且文本已变�?
text为改变后的文�?iItem为行�?iSubItem为列�?此功能需要扩展listview并实现了编辑功能的的控件才能支持
返回false可中止更新显示文�?/
}

```

### winUiGridObject.onEditEnd(iItem,iSubItem)

```aardio aardio
winUiGridObject.onEditChanged = function(iItem,iSubItem){
    /*控件完成编辑*/
}

```

### winUiGridObject.onFocusedChanged

```aardio aardio
winUiGridObject.onFocusedChanged = function(item,subItem,nmListView){
    /*焦点项变更触发此事件�?item 为变更为焦点的项序号，subItem 为列序号，nmListView �?NMLISTVIEW 结构�?/
}

```

### winUiGridObject.onGetDispItem

```aardio aardio
winUiGridObject.onGetDispItem = function(item,row,col){
    /*处理 _LVN_GETDISPINFOW 通知消息
参数 @item �?LVITEM 结构�?@row 为当前行�?@col 为当前列�?
返回 item 或包�?item 部分字段则更�?LVITEM 结构�?/
    return {text="要显示的文本"};
}

```

### winUiGridObject.onItemChanged

```aardio aardio
winUiGridObject.onItemChanged = function(item,subItem,nmListView){
    /*项目变更触发此事件�?item 为变更为焦点的项序号，subItem 为列序号，nmListView �?NMLISTVIEW 结构�?/
}

```

### winUiGridObject.onRightClick

```aardio aardio
winUiGridObject.onRightClick = function(item,subItem,nmListView){
    /*右键点击项目触发此事件�?item 为变更为焦点的项序号，subItem 为列序号，nmListView �?NMLISTVIEW 结构�?/
}

```

### winUiGridObject.onSelChanged

```aardio aardio
winUiGridObject.onSelChanged = function(selected,item,subItem,nmListView){
    /*选中项更触发此事件�?selected 为是否选中，item 为变更项序号�?subItem 为列序号，nmListView �?NMLISTVIEW 结构�?/
}

```

### winUiGridObject.onSortColumn(column,desc)

```aardio aardio
winUiGridObject.onSortColumn = function(column,desc){
    /*点击列排序时回调此函�?@column参数为列序号�?为首列，@desc参数指定是否倒序
返回true排序，否则不排序*/
    return true;
}

```

### winUiGridObject.setColumn({cx=100},列序�?

改变列宽，参数@1必须是个表对�?
### winUiGridObject.setColumn(列参数表,列序�?

参数一指定 wLVCOLUMN 结构体成员键值的参数�?

也可以是LVCOLUMN结构体对�?自动设置掩码参数.

### winUiGridObject.setColumnText(位置,文本)

设置指定列文�?
### winUiGridObject.setColumnWidth(列宽,列序�?...)

设置列宽，可指定一个或多个列序号�?
这里不能指定宽度�?-1 �?
### winUiGridObject.setColumns()

用一个字符串数组指定要显示的�?
如果参数为空则清空所有列

### winUiGridObject.setReadonlyColumns()

可以使用一个或多个参数指定要禁止编辑的列序号，

也可以用一个数组参数指定多个列序号�?
如果参数�?-1，则禁止编辑所有列

### winUiGridObject.setTable

�?listview 控件显示数据表（包含名值对的对象或数组组成的数组）�?
此函数会自动清空控件之前的所有项�?
如果没有创建任何列，则自动创建标题列�?
如果要重新创建列，请先调�?clear 函数并指定参数为 true 以清空原来的列�?
### winUiGridObject.setTable(dataTable)

参数 @dataTable 指定要加载的数据表�?
数据表应当包含行组成的数组�?
数据行可以是数组，也可以是名值，值用 tostring 转为文本显示�?
可选通过数据表的 fields 字段指定要显示的索引数组（键名或索引数值）�?
如果视图控件的标题列为空，则用显示键名（或数组值）创建标题列�?
如果数据行为数组，第一行填充到标题列以后，默认从第二行加载数据�?
可用 startIndex 属性或元属性自定义要加载的起始行�?
可用 length 属性自定义要加载的行数，默认加载所有行�?
sqlite,access,sqlServer 等数据库对象�?
提供�?getTable 函数可获取通过 fields 字段指定列名数组的数据表�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/win/ui/grid.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/win/ui/grid.md')

