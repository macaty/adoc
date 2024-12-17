[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: richedit修改行距

```aardio aardio
//文本框修改边距行�?import win.ui;
/*DSG{{*/
var winform = win.form(text="richedit修改行距";right=759;bottom=469)
winform.add(
richedit={cls="richedit";left=174;top=64;right=603;bottom=384;db=1;dl=1;dr=1;dt=1;edge=1;multiline=1;z=1}
)
/*}}*/

//修改文本框边�?winform.richedit.setPadding(20,20,20,20);

/*
PARAFORMAT2提供的功能要么是摆设（richedit并不支持�?要么一般用不到�?对排版有需求的建议改用浏览器控件，下面以修改行距为例演示一下这个结构体的用法�?*/
class PARAFORMAT2 {
    INT cbSize = 188;
    INT mask;
    WORD numbering;
    WORD effects;
    int dxStartIndent;
    int dxRightIndent;
    int dxOffset;
    WORD alignment;
    WORD cTabCount;
    int rgxTabs[32];
    INT dySpaceBefore;
    INT dySpaceAfter;
    INT dyLineSpacing;
    WORD style;
    BYTE lineSpacingRule;
    BYTE outlineLevel;
    WORD shadingWeight;
    WORD shadingStyle;
    WORD numberingStart;
    WORD numberingStyle;
    WORD numberingTab;
    WORD borderSpace;
    WORD borderWidth;
    WORD borders;
};

var pf = PARAFORMAT2();
pf.mask = 0x100/*_PFM_LINESPACING*/;
pf.lineSpacingRule = 4;
pf.dyLineSpacing = 24 * 20;
winform.richedit.sendMessage(0x447/*_EM_SETPARAFORMAT*/,,pf)

winform.richedit.text =/*
一�?又一�?*/

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Edit/lineSpacing.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Edit/lineSpacing.md')

