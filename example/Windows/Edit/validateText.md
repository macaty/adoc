[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 文本�?- 校验输入文本

```aardio aardio
//文本�?- 校验输入文本
import win.ui;
/*DSG{{*/
var winform = win.form(text="文本框限制输入金�?;right=759;bottom=469)
winform.add(
edit={cls="edit";left=140;top=136;right=483;bottom=163;align="right";edge=1;z=1}
)
/*}}*/

//�?winform.edit 控件内关闭输入法避免误输非英文字�?winform.edit.disableInputMethod();

//设置默认输入提示，文本为空且控件失去焦点时显�?winform.edit.setCueBannerText("请输入金�?);

//控件文本变更时触�?onChange 事件
winform.edit.onChange = function(){

    /*
    下面的函数用于限制编辑框只能输入数值，并且只能是表示货币金额的数值�?    如果输入错误则自动修正输入文本，并将输入光标移动到文本尾部并在编辑框内用气泡提示显示错误文本�?
    用参�?@1 指定的模式串匹配与校验输入文本，
    用参�?@2 指定输入错误时显示的气泡提示文本�?    */
    winform.edit.validateText("<\d+\.\d\d>|<\d+\.\d>|<\d+\.>|<\d+>",
        "不能接受的字�?,"只能在此输入金额，小数点后不能超�?2 �?");
}

//显示窗体
winform.show();

//启动界面线程消息循环
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Edit/validateText.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Edit/validateText.md')

