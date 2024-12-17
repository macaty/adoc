[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# win.ui.listEdit 库模块帮助文�?
## win.ui 成员列表

### win.ui.listEdit()

参数必须指定一�?listbox 控件对象

返回一个可编辑单元格的列表框对�?

鼠标左键双击单元格、或者按空格键开始编�?

回车完成编辑,ESC键撤消编�?回车+上下方向键快速移动到其他�?

用户完成编辑后会触发onEditChanged事件

[返回对象:winuilstEditObject](#winuilstEditObject)

## winuilstEditObject 成员列表

### winuilstEditObject.beginEdit(列表项索�?

切换到编辑模式，可选用参数 @1 指定列表项索引�?
不指定则自动获取，指定为 0 则在列表尾部新增项目并切换到编辑模式�?
新增项目如果不输入内容则自动删除�?
### winuilstEditObject.editBox

实现编辑功能的edit控件

此功能需要扩展listview并实现了编辑功能的的控件才能支持

[返回对象:editObject](ctrl/edit.html#editObject)

### winuilstEditObject.onEditChanged(newText,selIndex)

```aardio aardio
winuilstEditObject.onEditChanged = function(newText,selIndex){
    /*控件完成编辑
text为更新后的文�?selIndex为行�?返回false取消编辑*/
}

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/win/ui/listEdit.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/win/ui/listEdit.md')

