[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 可编辑列表框控件（listbox�?
```aardio aardio
//可编辑列表框控件（listbox�?import win.ui;
/*DSG{{*/
var winform = win.form(text="可编辑listbox演示";right=744;bottom=475)
winform.add(
btnAddItem={cls="button";text="添加";left=444;top=414;right=634;bottom=453;z=2};
listbox={cls="listbox";left=41;top=15;right=703;bottom=402;edge=1;items={};z=1}
)
/*}}*/

import win.ui.listEdit;
var listEdit = win.ui.listEdit(winform.listbox);

//编辑完成时触发此事件，newText 为新文本，selIndex 为编辑的项目索引
listEdit.onEditChanged = function(newText,selIndex){

}

/*
在列表项上双击可切换到编辑模式�?编辑模式�?ESC 撤消，按 Enter、点击编辑框外面、编辑框失去焦点都可以完成编辑�?*/
winform.listbox.items = {
  "双击这里启动编辑";
  "文本框失去焦点自动完成编�?;
  "回车也可以完成编�?;
  "按ESC可以取消编辑";
}

winform.btnAddItem.oncommand = function(id,event){
    //不指定索引编辑当前选项，索引为 0 则增加临时项并切换到编辑模式，不输入内容则删除临时项�?    listEdit.beginEdit(0)
}

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Listbox/listEdit.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Listbox/listEdit.md')

