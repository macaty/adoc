[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 富文本框（richedit�?- 查找替换

```aardio aardio
//富文本框（richedit�?- 查找替换
import win.ui;
/*DSG{{*/
var winform = win.form(text="richedit - 使用查找替换对话�?;right=1071;bottom=815)
winform.add(
btnFind={cls="button";text="查找";left=732;top=755;right=860;bottom=798;db=1;dr=1;z=2};
btnReplace={cls="button";text="替换";left=871;top=755;right=999;bottom=798;db=1;dr=1;z=3};
richedit={cls="richedit";text="richedit richedit richedit richedit richedit richedit richedit richedit richedit richedit ";left=27;top=11;right=1049;bottom=728;db=1;dl=1;dr=1;dt=1;edge=1;hidesel=false;multiline=1;z=1}
)
/*}}*/

import win.dlg.findReplace;
var frDlg = win.dlg.findReplace(winform);

frDlg.onSearch = function(findWhat,down,matchCase,wholeWord){
    winform.richedit.findText(findWhat,frDlg.flags);
}

frDlg.onReplace = function(findWhat,replaceWith,down,matchCase,wholeWord){
    winform.richedit.replaceText(findWhat,replaceWith,frDlg.flags);
}

frDlg.onReplaceAll = function(findWhat,replaceWith,down,matchCase,wholeWord){
    winform.richedit.replaceAll(findWhat,replaceWith,frDlg.flags)

}

winform.btnFind.oncommand = function(id,event){
    frDlg.find(winform.richedit.selText)
}

winform.btnReplace.oncommand = function(id,event){
    frDlg.replace(winform.richedit.selText);
}

winform.show()
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Edit/findReplace.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Edit/findReplace.md')

