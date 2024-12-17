[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 使用拆分�?splitter)控件在窗口上拆分多个控件

```aardio aardio
//拆分控件
import win.ui;
/*DSG{{*/
var winform = win.form(text="使用拆分�?splitter)控件在窗口上拆分多个控件";right=801;bottom=486)
winform.add(
custom={cls="custom";text="自定义控�?;left=214;top=8;right=791;bottom=475;db=1;dl=1;dr=1;dt=1;z=3};
edit={cls="edit";text="edit";left=4;top=8;right=204;bottom=194;db=1;dl=1;dt=1;edge=1;multiline=1;z=1};
edit2={cls="edit";text="edit";left=4;top=205;right=204;bottom=475;db=1;dl=1;dt=1;edge=1;multiline=1;z=4};
splitterHorz={cls="splitter";left=5;top=197;right=204;bottom=202;dl=1;frame=1;horz=1;z=5};
splitterVert={cls="splitter";left=204;top=8;right=212;bottom=475;db=1;dl=1;dt=1;frame=1;z=2}
)
/*}}*/

//指定需要拆分的控件（拖动拆分条可改变被拆分控件的大小）
winform.splitterHorz.split(winform.edit,winform.edit2);

//指定需要拆分的控件，参数也可以指定包含多个控件的数�?winform.splitterVert.split( {
    winform.edit,winform.edit2,winform.splitterHorz //数组中的控件须位于拆分条同一�?    },winform.custom )

winform.splitterVert.ltMin = 20; //左边控件最小宽�?winform.splitterVert.rbMin = 500; //右边控件最小宽�?
/*
如果想拆分更多控件，
也可以用 custom 控件作为容器加载子窗口即可�?
可以�?winform.custom.loadForm() 函数加载子窗口，
也可以直接在 custom 控件的类名属性中指定子窗口的路径�?*/
winform.custom.loadForm("~/example/plus/disabledText.aardio")

//拆分条拖拽移动到新位置时触发此事年，l,t,r,b 分别为拆分条当前左、上、右、下坐标�?winform.splitterVert.onSplitterMoved = function(l,t,r,b){

}

winform.show()
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Controls/splitter.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Controls/splitter.md')

