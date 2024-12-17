[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# FlaUI.UIA3.Caret 库模块帮助文�?
## FlaUI.UIA3.Caret 成员列表

### FlaUI.UIA3.Caret.Get

获取输入光标位置�?
此函数功能与用法 winex.caret.get 函数完全一�?
### FlaUI.UIA3.Caret.Get()

[返回对象:rectObject](../global/_.html#rectObject)

### FlaUI.UIA3.Caret.Get(hwnd)

�?@hwnd 指句柄的窗口获取输入光标位置�?
不指定参数则获取前台窗口输入光标�?
成功返回 ::RECT 结构体，失败返回 null�?
返回结构体的值使用屏幕坐标�?
如果获取到真实输入光标大小则返回结构体的 right,bottom 为非 0 值，

如果�?I 光标位置�?right,bottom 值为 0�?
返回结构体的 hwnd 成员为输入光标所在窗口句柄�?
�?2 个返回值为输入焦点窗口句柄

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/FlaUI/UIA3.Caret.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/FlaUI/UIA3.Caret.md')

