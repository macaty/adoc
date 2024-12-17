[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: dsoFramer 嵌入 Office 文档

```aardio aardio
//dsoFramer 嵌入 Office 文档
/*
DsoFramer 是微软开源的控件用于嵌入 Word�?Excel�?PPT 文档�?这个控件是开源的，一般还是够用的。并且这个扩展库已经实现了免注册调用，支持生成独立EXE文件�?而且这个控件的体积非常小�?
但是要注意微软已经不维护这个控件了，
如果你还有更多的改进想法，可自行到网上下�?DsoFramer 源码并进行改进�?*/
import win.ui;
/*DSG{{*/
mainForm = win.form(text="dsoFrame控件测试";right=1191;bottom=769;bgcolor=16448250)
mainForm.add(
btnExcel={cls="button";text="创建表格";left=40;top=710;right=162;bottom=755;db=1;dl=1;z=2};
button={cls="button";text="打开文档、表格、或幻灯�?;left=187;top=711;right=384;bottom=756;db=1;dl=1;z=6};
chkMenubar={cls="checkbox";text="显示菜单�?;left=613;top=721;right=716;bottom=748;bgcolor=16448250;z=3};
chkTitlebar={cls="checkbox";text="显示标题�?;left=930;top=721;right=1033;bottom=748;bgcolor=16448250;z=5};
chkToolbars={cls="checkbox";text="显示工具�?;left=771;top=721;right=874;bottom=748;bgcolor=16448250;z=4};
custom={cls="custom";text="自定义控�?;left=0;top=7;right=1186;bottom=690;bgcolor=16777215;db=1;dl=1;dr=1;dt=1;z=1}
)
/*}}*/

mainForm.show(0x3/*_SW_MAXIMIZE*/);

import com.dsoFramer;
var dsoFrame = com.dsoFramer(mainForm.custom)
dsoFrame.menubar = false //去掉菜单�?dsoFrame.titlebar = false; //去掉标题�?dsoFrame.toolbars = false; //去掉工具�?dsoFrame.borderStyle = 0; //去掉边框（默认值）

//新建或打开文档触发此事�?dsoFrame.OnDocumentOpened = function( path, document){
    mainForm.text = #path ? path : "新文�?
}

mainForm.btnExcel.oncommand = function(id,event){
    dsoFrame.createNewExcel();
    dsoFrame.activeDocument.Sheets(1).Cells(1,1).Value2 = "测试一�?;

    //监听文档事件
    com.Connect(dsoFrame.activeDocument,{
        SheetSelectionChange = function(sheet,targetRange){

        };
        SheetBeforeDoubleClick = function(sheet,targetRange,Cancel){

        };
        SheetChange = function(sheet,targetRange){
            //https://docs.microsoft.com/en-us/office/vba/api/excel.workbook.sheetchange
            mainForm.text = "修改了："+ targetRange.getValue2();
        };
    })
}

mainForm.chkMenubar.oncommand = function(id,event){
    dsoFrame.menubar = mainForm.chkMenubar.checked;
}

mainForm.chkToolbars.oncommand = function(id,event){
    dsoFrame.toolbars = mainForm.chkToolbars.checked;
}

mainForm.chkTitlebar.oncommand = function(id,event){
    dsoFrame.titlebar = mainForm.chkTitlebar.checked;
}

import fsys.dlg;
mainForm.button.oncommand = function(id,event){
    var path = fsys.dlg.open("Word 文档|*.doc;*.docx|Excel 表格|*.xls;*.xlsx|演示文稿|*.ppt;*.pptx||","打开 Office 文档");
    if(path) {
        dsoFrame.openFile(path);

        //如果打开的是 PPT
        if(dsoFrame.activeDocumentTypeName() == "PowerPoint"){
            //自动全屏播放
            dsoFrame.activeDocument.SlideShowSettings.Run();
        }
    }
}

/*
dsoFrame.activeDocument 的用法：

Word 文档对象请参考：
https://docs.microsoft.com/en-us/office/vba/api/word.document

Excel 文档对象请参考：
https://docs.microsoft.com/en-us/office/vba/api/excel.workbook

PowerPoint 文档对象请参考：
https://docs.microsoft.com/en-us/office/vba/api/powerpoint.presentation
*/
return win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/COM/Others/DsoFramer.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/COM/Others/DsoFramer.md')

