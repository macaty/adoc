[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: radiobutton单选按钮分组演�?
```aardio aardio
//单选按�?import win.ui;
/*DSG{{*/
var winform = win.form(text="radiobutton单选按钮分组演�?;right=759;bottom=469)
winform.add(
groupbox={cls="groupbox";text="单选控件分组一(控件右对齐，固定右边�?";left=43;top=11;right=432;bottom=186;aw=1;edge=1;z=2};
groupbox2={cls="groupbox";text="单选控件分�?，控件左对齐，下对齐，使用固定左、下边距实现";left=320;top=266;right=706;bottom=445;aw=1;edge=1;z=1};
radiobutton={cls="radiobutton";text="radiobutton";left=199;top=61;right=282;bottom=93;dr=1;dt=1;z=3};
radiobutton2={cls="radiobutton";text="radiobutton2";left=335;top=399;right=443;bottom=431;db=1;dl=1;z=4};
radiobutton3={cls="radiobutton";text="radiobutton3";left=302;top=61;right=395;bottom=93;dr=1;dt=1;z=5};
radiobutton4={cls="radiobutton";text="radiobutton4";left=479;top=399;right=587;bottom=431;db=1;dl=1;z=6};
static={cls="static";text="static";left=42;top=199;right=700;bottom=257;transparent=1;z=7}
)
/*}}*/

//自动调用所有groupbox的group函数,使groupbox范围内的窗口自动设为groupbox的子窗口
winform.group();

winform.static.text =/*
默认顺序添加控件，保持控件按Z序（添加顺序、或前后排序）排列，
每组的第一个控件将编组属性设为true，或者放一个groupbox都可以�?
我们这里演示的方法并没有使用Z序分组，
而是直接把radiobutton所在的groupbox设为父窗口，也可以简洁直观的对控件进行分组�?*/

winform.radiobutton4.oncommand = function(id,event){
    winform.text = owner.text;
}

winform.radiobutton2.oncommand = function(id,event){
    winform.text = owner.text;
}

winform.radiobutton3.oncommand = function(id,event){
    winform.text = owner.text;
}

winform.radiobutton.oncommand = function(id,event){
    winform.text = owner.text;
}

winform.show()
win.loopMessage();

winform.enumControl( function(ctrl){

})

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Controls/radio.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Controls/radio.md')

