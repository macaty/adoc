[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 窗口动画演示

```aardio aardio
//窗口动画演示
import win.ui;
/*DSG{{*/
var winform = win.form(text="动画窗口演示";right=400;bottom=202;max=false;min=false)
winform.add()
/*}}*/

import win.animate;
win.animate.fade( winform ).show()

winform.onClose = function(hwnd,message,wParam,lParam){
    win.animate.roll(winform).hide()
}

win.loopMessage();
return winform;

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Effects/animate.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Effects/animate.md')

