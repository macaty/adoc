[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 窗口程序 - 遮罩效果

```aardio aardio
//窗口程序 - 遮罩效果
import win.ui;
/*DSG{{*/
var winform = win.form(text="遮罩示例";right=759;bottom=469)
winform.add(
button={cls="button";text="显示遮罩";left=416;top=80;right=624;bottom=160;z=1};
edit={cls="edit";text="edit";left=112;top=192;right=528;bottom=304;edge=1;multiline=1;z=2}
)
/*}}*/

import win.ui.mask;
var frmMask = win.ui.mask(winform,true)
winform.button.oncommand = function(id,event){
    winform.button.disabledText = "窗口客户区禁用中..."
    frmMask.show(true); //显示遮罩

    win.delay(2000);
    winform.button.disabledText = null;
    frmMask.show(false); //隐藏遮罩
}

winform.show()
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Effects/mask.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Effects/mask.md')

