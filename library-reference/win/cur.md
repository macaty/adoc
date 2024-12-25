[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# win.cur 库模块帮助文�?
## win.cur 成员列表

### win.cur.beginCur()

持续设置当前鼠标指针句柄为最后一次使用load或loadfile加载的鼠标指针句�?
建议使用win.ui.waitCursor替代此函�?
### win.cur.beginCur(hCur)

持续设置当前鼠标指针句柄

直到调用win.cur.endCur()

hcur为鼠标指针句�?
### win.cur.beginWaitCur()

持续设置鼠标指针为等待指�?直到调用win.cur.endCur

建议使用win.ui.waitCursor替代此函�?
### win.cur.beginning

如果调用了beginCur或beginWaitCur

在尚未调用endCur之前beginning返回true

### win.cur.endCur()

恢复默认鼠标指针

建议使用win.ui.waitCursor替代此函�?
### win.cur.getCur()

返回当前鼠标指针句柄

### win.cur.load(id)

载入鼠标指针资源,返回鼠标指针句柄

id为资源ID,或资源名�?
### win.cur.load(id,instance)

载入鼠标指针资源,返回鼠标指针句柄

id为资源ID,或资源名�?
instance为DLL模块句柄

### win.cur.loadfile("字符串参�?)

载入鼠标指针文件,返回鼠标指针句柄

### win.cur.setCur()

设置为最后一次使用load或loadfile加载的鼠标指针句�?
### win.cur.setCur(hCur)

设置当前鼠标指针句柄

hcur为鼠标指针句�?
此函数一般用于回调函数中响应\_WM\_SETCURSOR消息

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/win/cur.md)

