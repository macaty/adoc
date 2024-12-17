[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# win.inputBox 库模块帮助文�?
## win 成员列表

### win.inputBox

输入对话�?
创建一个输入对话框

### win.inputBox()

[返回对象:wininputBoxObject](#wininputBoxObject)

### win.inputBox(父窗�?密码模式�?
创建一个输入对话框,所有参数可�?
设置密码模式输入框输入内容显示为星号

## wininputBoxObject 成员列表

### wininputBoxObject.bgcolor

设置窗口背景颜色�?
使用 GDI 颜色值，例如 0xFFFFFF 为白�?
### wininputBoxObject.center()

居中显示

### wininputBoxObject.changeInterval(请输入ID,1000)

重新设定定时器的延时时间

### wininputBoxObject.clearInterval(请输入ID)

删除定时�?
### wininputBoxObject.doModal()

弹出输入对话�?
该函数返回用户输入的�?
取消则返回null空�?
### wininputBoxObject.dpiScale(x,y)

�?@x,@y 表示的像素值乘以窗体当�?DPI 缩放倍数并返�?

省略 @y 参数时仅返回 @x 转换后的�?
### wininputBoxObject.getPos()

返回相对坐标,�?�?
### wininputBoxObject.info

[返回对象:editObject](ui/ctrl/edit.html#editObject)

### wininputBoxObject.input

[返回对象:editObject](ui/ctrl/edit.html#editObject)

### wininputBoxObject.modifyStyle(remove,add,swpFlags)

修改窗口样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### wininputBoxObject.modifyStyleEx(remove,add,swpFlags)

修改窗口扩展样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS\_EX_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS\_EX_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### wininputBoxObject.onInitDialog

```aardio aardio
wininputBoxObject.onInitDialog = function(hwnd,message,wParam,lParam){
    wininputBoxObject.center()/*输入框初始化完成触发该函�?/
}

```

### wininputBoxObject.setInterval(回调函数,延时毫秒�?...)

```aardio aardio
wininputBoxObject.setInterval(回调函数,延时毫秒�?...setInterval(
    function(){
        /*参数@1指定执行函数,参数@2指定执行间隔�?可选指定一个或多个回调参数，不指定回调参数则默认为:
 hwnd,message,timerId,tick,

如果在定时器中执行了win.delay等继续消息循环的代码�?在定时器退出前不会再触发同一定时器（重入）�?
定时器回调函数返回数值可修改时间间隔,
返回false取消该定时器*/
    },1000
)

```

### wininputBoxObject.setPos(x,y,�?�?插入位置,参数)

调整窗口位置或排�?
所有参数可�?
### wininputBoxObject.setTimeout(函数�?延时,其他参数)

延时执行函数

### wininputBoxObject.text

输入框标�?
### wininputBoxObject.topmost()

窗体始终最�?
### wininputBoxObject.topmost(false)

取消窗体始终最�?
### wininputBoxObject.width

设置对话框宽度�?
在窗口显示或其他方式自动或手动调�?enableDpiScaling 前修改此值，

则会�?enableDpiScaling 被调用时自动缩放�?
否则设置或获取当前真实宽度�?
可调�?dpiScale 函数获取缩放后的宽度

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/win/inputBox.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/win/inputBox.md')

