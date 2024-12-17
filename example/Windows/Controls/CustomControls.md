[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 自定义控件演�?
```aardio aardio
import win.ui;
import win.ui.ctrl.custom;
/*DSG{{*/
var winform = ..win.form(text="自定义控件演�?;right=587;bottom=494)
winform.add(
custom={cls="custom";text="custom";left=12;top=11;right=571;bottom=478;frame=1;transparent=1;z=1}
)
/*}}*/

winform.custom.add(
edit={cls="edit";text="edit";left=-1;top=-1;right=558;bottom=466;db=1;dl=1;dr=1;dt=1;edge=1;multiline=1;z=1}
)

winform.custom.edit.text = /*
第一步：
--------------------------------------------------
按CTRL + U切换到窗体设计器,
从【工具箱/界面控件/最后一个控件图标】拖一个自定义控件到窗体上�?
第二步：
--------------------------------------------------
点击窗体上的自定义控�?
点选右侧属性面板的【类名】属�?修改控件类名,例如"custom"

在win.ui.ctrl 名字空间增加一个自定义控件类库,类名为上面设定的类名,
例如"custom"控件就需要增�?win.ui.ctrl.custom;

注意自定义控件必须显式的导入到当前代码中,
例如import win.ui.ctrl.custom;(添加在import win.ui;后面)

第三步：
--------------------------------------------------
然后在自定义控件类中编写代码,
在类的构造函数中创建对象,对象必须使用hwnd属性指定创建成功的子窗口句柄�?子窗口可以是调用API创建的子窗口,或者其他win.form对象也可�?窗体上上也可以组合其他控�?�?可选为自定义控件添加成员函数等�?大家可以在标准库中打开 win.ui.ctrl.custom 控件的源码�?*/

winform.show(true)
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Controls/CustomControls.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Controls/CustomControls.md')

