[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 在富文本框输入带颜色字体

```aardio aardio
//修改颜色样式
import win.ui;
/*DSG{{*/
var winform = win.form(text="在富文本框输入带颜色字体";right=759;bottom=469)
winform.add(
button={cls="button";text="输入指定颜色字体";left=502;top=412;right=667;bottom=458;z=2};
richedit={cls="richedit";left=25;top=15;right=716;bottom=398;edge=1;multiline=1;z=1}
)
/*}}*/

//响应按钮事件
winform.button.oncommand = function(id,event){

    /*
    追加文本，支持任意个文本参数�?    可插入任意个样式表参数，如果指定了样式表，函数返回前恢复默认样式�?    样式表指�?CHARFORMAT2 结构体部分需要修改的字段即可�?    用法细节参考库函数文档�?
    常用字段�?    - backColor: 背景颜色，GDI 颜色格式�?0xBBGGRR ）�?    - textColor: 字体颜色，GDI 颜色格式�?0xBBGGRR ）�?    - faceName: 字体�?    - point: 字体大小，以 pt 为单�?    - italic = 是否斜体，仅用于写入样式�?    - strikeout = 是否显示删除线，仅用于写入样式�?    - underlineType: 下划线类�?    - underline = 是否粗体，仅用于写入样式�?    */
    winform.richedit.appendText(
        { textColor = 0xFF0000 },
        " ","蓝色文本",
        {  protected = true, point = 16 },
        " ","绿色文本",
        { textColor = 0x0000FF,point = 8 },
        " ","红色文本1", " ","红色文本2", " ","红色文本3",
    );

    winform.richedit.appendText("默认样式");

    /*
    下面这样写也可以，等于传了一个表参数并省略了外层大括号{}�?    函数会自动展开参数表的数组成员作为其他调用参数，可指定多个文本参数�?    */
    winform.richedit.appendText( textColor = 0xFF0000, "蓝色文本" )

    //下面这样写作用一�?    winform.richedit.appendText( { textColor = 0xFF0000, "蓝色文本"} )

    //下面这样写也�?    winform.richedit.appendText({
        textColor = 0x00FF00;  // 使用 RGB 颜色值（0xBBGGRR 格式�?这里是绿�?        text = "这是绿色文本";
    })
}

//使用 TO 文本对象（COM 对象）设置样�?var textDoc = winform.richedit.createTextDocument()
textDoc.Selection.Text = "红色加粗"
textDoc.Selection.Font.ForeColor = gdi.RGB(255,0,0)  // 红色
textDoc.Selection.Font.Bold = textDoc.tomTrue  // 加粗

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Edit/CHARFORMAT2.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Edit/CHARFORMAT2.md')

