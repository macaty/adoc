[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: �?aardio 中使�?.NET 颜色�?System.Drawing.Color

```aardio aardio
//�?aardio 中使�?.NET 颜色�?System.Drawing.Color
import win.ui;
/*DSG{{*/
var winform = win.form(text="System.Drawing.Color";right=757;bottom=467)
winform.add(
plus={cls="plus";left=95;top=95;right=461;bottom=192;z=1}
)
/*}}*/

import System.Drawing; //建议右键点库名称 -> 跳转到定�?看看这个库的源代�?/*
System.Drawing.Color 是一�?struct 特例�?System.Drawing.Color �?aardio 会自动转换为 ARGB 格式的颜色数值�?调用 .NET �?ARGB 格式的颜色数值也能自动转换为 System.Drawing.Color 对象�?注意 GDI+ 使用 ARGB 格式颜色值，�?gdip库，plus 控件等兼容�?*/
winform.plus.background = System.Drawing.Color.Blue; //这是一�?.NET 里的枚举�?
winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/Color.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/Color.md')

