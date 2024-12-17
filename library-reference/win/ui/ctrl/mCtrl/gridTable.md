[aardio 文档](../../../../../index.htm "aardio 编程语言文档首页")

# win.ui.ctrl.mCtrl.gridTable 库模块帮助文�?
## mCtrlGridTableObject 成员列表

### mCtrlGridTableObject.addRef()

增加引用计数

### mCtrlGridTableObject.clear(行总数,列总数)

清空表格,

不指定清空全部内�?
\| 1 清空普通单元格,

\| 2 清空列标�?
\| 4 清空行标�?
### mCtrlGridTableObject.columnCount()

列总数

### mCtrlGridTableObject.getCell(行号,列号)

返回指定列的MC\_TABLECELL结构�?
行号省略表示列标题，列号省略表示行标�?
### mCtrlGridTableObject.getCellTextl(行号,列号)

返回指定列的文本

行号省略表示列标题，列号省略表示行标�?
### mCtrlGridTableObject.release()

减少引用计数

### mCtrlGridTableObject.resize(行总数,列总数)

调整表格大小

### mCtrlGridTableObject.rowCount()

行总数

### mCtrlGridTableObject.setCell(行号,列号,MC\_TABLECELL结构�?

设置格列，参数@3为MC\_TABLECELL结构�?
行号省略表示列标题，列号省略表示行标�?
### mCtrlGridTableObject.setCellAlign(行号,列号,对齐选项)

设置对齐选项,

参数@3应使用一个表指定对齐方式,

对齐表可用left,right,center指定水平对齐选项

可用top bottom,middle指定垂直对齐选项

指定的对齐选项字段值为真时使用该对齐方�?
### mCtrlGridTableObject.setCellText(行号,列号,文本)

设置列文�?
行号省略表示列标题，列号省略表示行标�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/win/ui/ctrl/mCtrl/gridTable.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/win/ui/ctrl/mCtrl/gridTable.md')

