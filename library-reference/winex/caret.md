[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# winex.caret 库模块帮助文�?
## winex.caret 成员列表

结合 winex.getUiInfo,winex.accObject.getCaret,::User32.GetCursorInfo

System.Windows.Automation.3 等多种接口获取当前输入光标位�?
### winex.caret.get

获取输入光标位置

### winex.caret.get()

[返回对象:rectObject](../global/_.html#rectObject)

### winex.caret.get(hwnd)

�?@hwnd 指句柄的窗口获取输入光标位置�?
不指定参数则获取前台窗口输入光标�?
成功返回 ::RECT 结构体，失败返回 null�?
返回结构体的值使用屏幕坐标�?
如果获取到真实输入光标大小则返回结构体的 right,bottom 为非 0 值，

如果�?I 光标位置�?right,bottom 值为 0�?
返回结构体的 hwnd 成员为输入光标所在窗口句柄�?
�?2 个返回值为输入焦点窗口句柄

### winex.caret.getPos(offsetX,offsetY)

返回输入光标或选区文本所在坐标，失败则返回鼠标指针坐标�?
返回值为分别表示 x,y 坐标的两个数值�?
可选用 offsetX,offsetY 参数分别指定返回 x,y 坐标的偏移值�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/winex/caret.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/winex/caret.md')

