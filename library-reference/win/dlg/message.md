[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# win.dlg.message 库模块帮助文�?
## win.dlg 成员列表

### win.dlg.message

简单信息提示框

导入时为当前线程所有窗口安装msgInfo,msgAsk,msgErr等msg前缀的消息框函数

此支持库主要用于演示,大家可以在此源码基础上改动为适合自己的用户库

### win.dlg.message()

[返回对象:winDlgMessageObject](#winDlgMessageObject)

### win.dlg.message(可选指定父窗口)

创建简单信息提示框

可选在参数中指定父窗口对象或父窗口句柄

也可以在创建对象后使用parent属性指�?

不指定父窗口时默认取当前线程活动窗口作为父窗�?
## winDlgMessageFormObject 成员列表

### winDlgMessageFormObject.beforeDestroy

```aardio aardio
winDlgMessageFormObject.beforeDestroy = function(){
    /*指定在窗体销毁以前执行的代码
早于onDestroy触发*/

}

```

### winDlgMessageFormObject.bgcolor

背景颜色

### winDlgMessageFormObject.btnCancel

取消按钮

[返回对象:uiCtrlPlusObject](../ui/ctrl/plus.html#uiCtrlPlusObject)

### winDlgMessageFormObject.btnOk

确定按钮

[返回对象:uiCtrlPlusObject](../ui/ctrl/plus.html#uiCtrlPlusObject)

### winDlgMessageFormObject.center(目标窗口句柄)

居中窗口,并调整以保证显示在可见范围内

目标窗口句柄如果为空则取父窗口或所有者窗�?�?表示桌面

### winDlgMessageFormObject.close()

关闭窗口

### winDlgMessageFormObject.doModal(/\*请指定所有者窗口\\n可省略此参数\*/)

此函数弹出模态对话框

### winDlgMessageFormObject.endModal(请指定模态对话框返回�?

关闭模态对话框�?
调用endModal()函数的参数会被设置为 doModal()函数的返回值�?
### winDlgMessageFormObject.hwnd

窗口句柄

句柄是一个数值，用于标识一种系统资源，如窗口、位图等等，

如果你要操作一种系统资源，必须先获得句柄�?
句柄在aardio中通常转换为指�?pointer)类型�?
而窗口句柄是个特例，onDestroy = @.onDestroy = function(){

\_\_/\*指定在窗体销毁以前执行的代码\*/

}

### winDlgMessageFormObject.icon

显示文字图标的plus控件

[返回对象:uiCtrlPlusObject](../ui/ctrl/plus.html#uiCtrlPlusObject)

图标控件

[返回对象:uiCtrlPlusObject](../ui/ctrl/plus.html#uiCtrlPlusObject)

### winDlgMessageFormObject.message

显示文本消息的plus控件

[返回对象:uiCtrlPlusObject](../ui/ctrl/plus.html#uiCtrlPlusObject)

### winDlgMessageFormObject.onMouseClick

```aardio aardio
winDlgMessageFormObject.onMouseClick = function(wParam,lParam){
    var x,y = win.getMessagePos(lParam);/*在窗口上单击并弹起鼠标左键触发此事件*/
}

```

### winDlgMessageFormObject.progress

进度�?plus控件

[返回对象:uiCtrlPlusObject](../ui/ctrl/plus.html#uiCtrlPlusObject)

### winDlgMessageFormObject.setInterval(回调函数,延时毫秒�?...)

```aardio aardio
winDlgMessageFormObject.setInterval(回调函数,延时毫秒�?...setInterval(
    function(){
        /*参数@1指定执行函数,参数@2指定执行间隔�?可选指定一个或多个回调参数，不指定回调参数则默认为:
 hwnd,message,timerId,tick,

如果在定时器中执行了win.delay等继续消息循环的代码�?在定时器退出前不会再触发同一定时器（重入）�?
定时器回调函数返回数值可修改时间间隔,
返回false取消该定时器*/
    },1000
)

```

### winDlgMessageFormObject.setPos(x坐标,y坐标,�?�?插入位置,参数)

调整窗口位置或排�?所有参数可�?
同时指定x,y坐标则移动位�?
同时指定宽高则改变大�?
指定插入位置(句柄或\_HWND前缀常量)则调整Z�?
### winDlgMessageFormObject.setRect(rc)

设置窗口区块位置(::RECT结构�?

### winDlgMessageFormObject.show(false)

隐藏窗口

### winDlgMessageFormObject.show(true)

显示窗口

### winDlgMessageFormObject.text

窗口标题

### winDlgMessageFormObject.valid

窗口是否有效

如果用户关闭窗体则返回false

## winDlgMessageObject 成员列表

### winDlgMessageObject.ask()

显示询问提示�?
用户按确定或回车返回true，其他返回false或null

### winDlgMessageObject.bgcolor

窗口背景颜色,GDI数值格�?
### winDlgMessageObject.buttonStyle

```aardio aardio
winDlgMessageObject.buttonStyle = {
    color = {
        hover = 0xF0FFFFFF;
        active = 0x30FFFFFF;
        default = 0x90FFFFFF;
    }
    border = {
        default = {width=0;}
        hover = { bottom = 1;color= 0xF0FFFFFF; }
        focus = { bottom = 1;color= 0xF0FFFFFF; }
        active = { bottom = 1;color= 0x30FFFFFF; }
    }
}

```

### winDlgMessageObject.cancelLabel

取消按钮文本，支持fontAwesome图标

### winDlgMessageObject.create()

[返回对象:winDlgMessageFormObject](#winDlgMessageFormObject)

### winDlgMessageObject.create(显示信息,是否显示按钮,是否显示进度�?

创建信息�?返回窗体对象,

如果选择显示按钮则不会同时显示进度条

所有参数都是可选参�?
### winDlgMessageObject.doModal(显示信息,是否显示按钮)

创建信息�?并显示为模态窗�?
### winDlgMessageObject.err()

显示错误提示�?

可选使用参数@2指定延时自动关闭提示框的毫秒�?
### winDlgMessageObject.fadeDuration

淡出淡出动画时长

### winDlgMessageObject.fadeInterval

淡出淡出动画时间间隔,设为0不显示动�?
### winDlgMessageObject.frown()

显示皱眉图标提示�?

可选使用参数@2指定延时自动关闭提示框的毫秒�?
### winDlgMessageObject.great()

显示竖大拇指图标提示�?

可选使用参数@2指定延时自动关闭提示框的毫秒�?
### winDlgMessageObject.icon

Font Awesome字体图标,请使用\_FA\_前缀常量指定;

### winDlgMessageObject.iconColor

图标颜色,GDI数值格�?

### winDlgMessageObject.info()

显示提示�?

可选使用参数@2指定延时自动关闭提示框的毫秒�?
如果指定参数@3或更多参�?

则使用这些参数调�?string.format 格式化参数@1

### winDlgMessageObject.ok()

显示正确提示�?

可选使用参数@2指定延时自动关闭提示框的毫秒�?
### winDlgMessageObject.okLabel

确定按钮文本，支持fontAwesome图标

### winDlgMessageObject.parent

父窗�?
信息框显示在父窗口中�?

并在信息框关闭前禁用父窗�?
### winDlgMessageObject.show(显示信息)

= 创建信息�?并显示为非模态窗�?
### winDlgMessageObject.smile()

显示微笑图标提示�?

可选使用参数@2指定延时自动关闭提示框的毫秒�?
### winDlgMessageObject.sorry()

显示倒竖大拇指图标提示框,

可选使用参数@2指定延时自动关闭提示框的毫秒�?
### winDlgMessageObject.textColor

文本颜色,GDI数值格�?
### winDlgMessageObject.titlebarStyle

```aardio aardio
winDlgMessageObject.titlebarStyle = {
    color = {
        hover = 0xffffffff;
        active = 0x33ffffff;
        default = 0x66ffffff;
    }
}

```

### winDlgMessageObject.warn()

显示警告提示�?

可选使用参数@2指定延时自动关闭提示框的毫秒�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/win/dlg/message.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/win/dlg/message.md')

