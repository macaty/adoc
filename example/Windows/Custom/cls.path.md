[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 窗口程序 - 使用自定义控件加载外部子窗口

```aardio aardio
//窗口程序 - 使用自定义控件加载外部子窗口
import win.ui;

/*
1、在 aardio 工程里找到其他新建的窗体代码文件�?右键点击该文件，复制文件路径，例�?"/.res/frmChild1.aardio"

2、拖一�?custom 控件到窗口上,
点击该控件，在控件属性窗口修改类名为 "/.res/frmChild1.aardio"

图文教程: https://mp.weixin.qq.com/s/s95LlTis3lrVeD8EYNZD0w
*/
/*DSG{{*/
var winform = win.form(text="使用 custom 控件直接加载子窗口文�?;right=759;bottom=469)
winform.add(
custom={cls="\.res\frmChild1.aardio";text="自定义控�?;left=19;top=15;right=740;bottom=455;db=1;dl=1;dr=1;dt=1;z=1}
)
/*}}*/

winform.custom.edit.text = /*
运行后的 winform.custom 就是加载 "/.res/frmChild1.aardio" 创建的子窗口�?aardio 会自动将 frmChild1.aardio 创建的窗口改为子窗口，不需要添加任何代码�?这个子窗口也会自动继�?custom 控件的设计时属性，支持自适应缩放、固定边距等设置�?*/

winform.show();
win.loopMessage();
return winform;

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Custom/cls.path.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Custom/cls.path.md')

