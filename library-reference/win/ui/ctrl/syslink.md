[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# win.ui.ctrl.syslink 库模块帮助文�?
## win.ui.ctrl 成员列表

### win.ui.ctrl.syslink

超链接控件类

### win.ui.ctrl.syslink()

超链接控件�?
[返回对象:syslinkObject](#syslinkObject)

## syslinkObject 成员列表

### syslinkObject.\_parentForm

创建该控件的父窗口（win.form对象�?

设计时窗体容器是所有拖放在窗体上的控件�?\_parentForm,

即使窗口移除子窗口样式、更改父子关系，或以 orphanWindow显示,

控件�?\_parentForm 始终都不会改�?
[返回对象:winform](../_.html#winform)

### syslinkObject.adjust

```aardio aardio
syslinkObject.adjust = function( cx,cy,wParam ) {

};

```

### syslinkObject.adjust()

调整窗口 \- 自定义事件函�?
### syslinkObject.bottom

底部坐标

### syslinkObject.capture

是否捕获全局鼠标消息

### syslinkObject.changeInterval(定时器ID,间隔时间,回调函数)

重新设置间隔时间或回调函�?
### syslinkObject.className

运行时类�?
### syslinkObject.clearInterval(定时器ID)

删除定时�?
### syslinkObject.close()

关闭控件窗口

### syslinkObject.cls

设计时类�?
### syslinkObject.disabled

是否禁用

### syslinkObject.getClientRect()

控件客户区块位置(::RECT结构�?

[返回对象:rectObject](../../../global/_.html#rectObject)

### syslinkObject.getFont()

控件字体(::LOGFONT结构�?

[返回对象:logfontObject](#logfontObject)

### syslinkObject.getForm()

如果是窗体返回自�?
如果是控件则返回\_parentForm

[返回对象:winform](../_.html#winform)

### syslinkObject.getItem()

[返回对象:syslinklitemObject](#syslinklitemObject)

### syslinkObject.getItem(索引)

返回超链接设�?该值为 LITEM 结构体�?
参数指定获取第几个超链接的设置，默认值为 1�?
### syslinkObject.getParent()

返回父窗�?
[返回对象:syslinkObject](#syslinkObject)

### syslinkObject.getPos()

返回相对坐标,�?�?
x,y,cx,cy=win.getPos(hwnd)

### syslinkObject.getRect()

控件区块位置(::RECT结构�?

### syslinkObject.getRect(true)

控件屏幕区块位置(::RECT结构�?

### syslinkObject.height

高度

### syslinkObject.hide

控件是否隐藏

### syslinkObject.hwnd

控件句柄

### syslinkObject.id

控件 ID，注意这个不是指超链接的 ID�?
### syslinkObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/)

使窗口绘图区无效

### syslinkObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/,0)

使窗口绘图区无效

不刷新背�?
### syslinkObject.left

左侧坐标

### syslinkObject.link

创建、设置或者获取控件的第一个超链接地址�?
这个参数应当指定一个网址，可使用任意协议�?
### syslinkObject.modifyStyle(remove,add,swpFlags)

修改窗口样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### syslinkObject.modifyStyleEx(remove,add,swpFlags)

修改窗口扩展样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS\_EX_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS\_EX_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### syslinkObject.onHyperlinkClick

```aardio aardio
syslinkObject.onHyperlinkClick = function(nmSysLink,url,id,index){
    raw.execute(url);/*点击超链接回调此事件，可使用此代码打开超链接�?如果不指定回调函数，控件会默认调�?raw.execute 打开链接�?nmSysLink 为通知消息使用�?LITEM 结构体，一般忽略即可�?url 为触发的超链接地址，也就是 href 属性�?id 为触发的链接 ID，也就是 id 属性�?index 为索引，一个控件可以有多个超链接，第一个超链接索引�?1�?/
}

```

### syslinkObject.redraw()

刷新

### syslinkObject.right

右侧坐标

### syslinkObject.setFocus()

设置焦点

### syslinkObject.setFont(指定字体)

指定LOGFONT字体对象,或逻辑字体句柄

### syslinkObject.setFont(混入字体属�?

```aardio aardio
syslinkObject.setFont(point=10;name="宋体");

```

### syslinkObject.setInterval(回调函数,延时毫秒�?...)

```aardio aardio
syslinkObject.setInterval(回调函数,延时毫秒�?...setInterval(
    function(){
        /*参数@1指定执行函数,参数@2指定执行间隔�?可选指定一个或多个回调参数，不指定回调参数则默认为:
 hwnd,message,timerId,tick,

如果在定时器中执行了win.delay等继续消息循环的代码�?在定时器退出前不会再触发同一定时器（重入）�?
定时器回调函数返回数值可修改时间间隔,
返回false取消该定时器*/
    },1000
)

```

### syslinkObject.setItem(item)

修改超链接设�?参数�?getItem 函数返回�?LITEM 结构�?
### syslinkObject.setParent(控件对象)

改变父窗�?
### syslinkObject.setPos(x坐标,y坐标,�?�?插入位置,参数)

调整窗口位置或排�?所有参数可�?
同时指定x,y坐标则移动位�?
同时指定宽高则改变大�?
指定插入位置(句柄或\_HWND前缀常量)则调整Z�?
### syslinkObject.setRect(rc)

设置控件区块位置(::RECT结构�?

### syslinkObject.setRect(rc,true)

设置控件屏幕区块位置(::RECT结构�?

### syslinkObject.setRedraw(false)

禁止重绘

### syslinkObject.setRedraw(true)

恢复重绘

### syslinkObject.show(true)

显示控件

### syslinkObject.text

控件文本�?
此控件的文本属性支�?HTML 的超链接语法，也就是 a 标签�?
可选使�?href 属性设置超链接，可选使�?id 属性指定链�?ID�?
一个控件可以指定多个普通文本或者超链接，使用超链接索引区分�?
不支持其�?HTML 语法，例如换行应当直接换行而不是使�?`<br>` 换行�?
可使�?link 属性获取或设置第一个超链接地址�?
### syslinkObject.theme

外观主题,例如

winform.button.theme = "Explorer"

winform.button.theme = false

### syslinkObject.top

顶部坐标

### syslinkObject.translateAccelerator

```aardio aardio
syslinkObject.translateAccelerator = function(msg){
    /*返回是否快捷�?/
}

```

### syslinkObject.update()

重绘invalidate函数指定的区�?
### syslinkObject.width

宽度

## syslinklitemObject 成员列表

### syslinklitemObject.iLink

索引�?
一个控件可以有多个超链接，第一个超链接索引�?1�?
### syslinklitemObject.id

超链接的 ID 属性�?
### syslinklitemObject.mask

有效字段掩码�?
默认已设�?\_LIF\_ITEMINDEX \| \_LIF\_STATE \| \_LIF\_ITEMID \| \_LIF\_URL

### syslinklitemObject.state

状态，一般用不上�?
可选值为 \_LIS\_ENABLED, \_LIS\_FOCUSED, \_LIS\_VISITED �?
### syslinklitemObject.stateMask

有效状态掩�?
### syslinklitemObject.url

超链接的 URL 属性�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/win/ui/ctrl/syslink.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/win/ui/ctrl/syslink.md')

