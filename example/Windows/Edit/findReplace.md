[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 瀵屾枃鏈锛坮ichedit锛?- 鏌ユ壘鏇挎崲

```aardio aardio
//瀵屾枃鏈锛坮ichedit锛?- 鏌ユ壘鏇挎崲
import win.ui;
/*DSG{{*/
var winform = win.form(text="richedit - 浣跨敤鏌ユ壘鏇挎崲瀵硅瘽妗?;right=1071;bottom=815)
winform.add(
btnFind={cls="button";text="鏌ユ壘";left=732;top=755;right=860;bottom=798;db=1;dr=1;z=2};
btnReplace={cls="button";text="鏇挎崲";left=871;top=755;right=999;bottom=798;db=1;dr=1;z=3};
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

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Edit/findReplace.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Edit/findReplace.md')

