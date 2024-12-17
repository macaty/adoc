[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 简繁转换演�?
```aardio aardio
//简繁转换演�?import win.ui;
/*DSG{{*/
var winform = win.form(text="简繁转换演�?;right=653;bottom=473;topmost=1)
winform.add(
btnBig52Gbk={cls="button";text="BIG5繁转GBK简";left=473;top=397;right=602;bottom=440;z=5};
btnF2j={cls="button";text="UTF8繁转简";left=172;top=397;right=301;bottom=440;z=3};
btnGbk2Big5={cls="button";text="GBK转BIG5�?;left=322;top=397;right=451;bottom=440;z=4};
btnJ2f={cls="button";text="UTF8简转繁";left=22;top=397;right=151;bottom=440;z=2};
edit={cls="edit";left=14;top=14;right=628;bottom=374;edge=1;multiline=1;z=1}
)
/*}}*/

import string.conv;
winform.btnF2j.oncommand = function(id,event){
    winform.edit.text = string.conv.simplized(winform.edit.text)
}

winform.btnJ2f.oncommand = function(id,event){
    winform.edit.text = string.conv.traditionalized(winform.edit.text )
}

winform.btnBig52Gbk.oncommand = function(id,event){
    winform.btnBig52Gbk.disabled = true;

    var ansiStr = string.fromto(winform.edit.text,65001,0);
    ansiStr = string.conv.big5ToGbk(ansiStr);
    winform.edit.text = ansiStr;

    winform.btnGbk2Big5.disabled = false;
}

winform.btnGbk2Big5.oncommand = function(id,event){
    winform.btnGbk2Big5.disabled = true;

    var ansiStr = string.fromto(winform.edit.text,65001,0);
    ansiStr = string.conv.gbkToBig5( ansiStr );
    winform.edit.text = ansiStr;

    winform.btnBig52Gbk.disabled = false;
}

if( ::Kernel32.GetACP() == 950 ){
    winform.btnGbk2Big5.disabled = true;
}
else {
    winform.btnBig52Gbk.disabled = true;
}

winform.show()
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Text/conv.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Text/conv.md')

