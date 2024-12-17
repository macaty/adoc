[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# win.ui.ctrl.edit 库模块帮助文�?
## win.ui.ctrl 成员列表

### win.ui.ctrl.edit

文本框控件支持库

### win.ui.ctrl.edit()

文本框控�?
[返回对象:editObject](edit.html#editObject)

## editObject 成员列表

### editObject.\_defWindowProc(hwnd,message,wParam,lParam)

用于�?wndproc 回调中提前调用默认消息回调函�?

所有窗口和控件定义�?wndproc 回调以后会自动创建这个函�?

调用此函数以�?wndproc 必须指定�?null 返回�?

以避免再次重复调用默认回调函�?
### editObject.\_parentForm

创建该控件的父窗口（win.form对象�?

设计时窗体容器是所有拖放在窗体上的控件�?\_parentForm,

即使窗口移除子窗口样式、更改父子关系，或以 orphanWindow显示,

控件�?\_parentForm 始终都不会改�?
[返回对象:winform](../_.html#winform)

### editObject.addCtrl(tParam)

```aardio aardio
editObject.addCtrl(
    spin={
        cls="spin";marginRight=4;marginTop=1;marginBottom=4;width=16;
        oncommand = function(id,event,pos){
            if( pos & event == 0x4/*_SB_THUMBPOSITION*/ ){
                winform.edit.text = string.format("%.2f",pos / 100 )
            }
        }
    }
)/*在edit控件窗口内添加子窗口*/

```

### editObject.adjust

```aardio aardio
editObject.adjust = function( cx,cy,wParam ) {
    /*窗口缩放时会自动触发此函数�?cx 参数为窗口宽�?cy 参数为窗口高�?
wParam 参数请参�?_WM_SIZE 消息参数说明,一般不用管�?
所�?win.form 创建的窗体和控件都支持此事件,
重复赋值只会追加而不会覆盖此事件�?一般不建议添加一�?wndproc 仅仅是为了处�? _WM_SIZE 消息�?定义 adjust 事件是更好的选择�?
可主动调用此事件,省略参数�?cx,cy 参数默认设为窗口大小*/
};

```

### editObject.appendText

追加文本并移动光标插入点到文本尾部�?
### editObject.appendText(追加文本-..)

追加文本并移动光标插入点到文本尾部�?
可指定零个、或多个参数，参数可以是字符串、buffer、数值�?
传入其他类型参数会抛出异常�?
返回文本总长�?
### editObject.bgcolor

获取或修改景颜色数�?
### editObject.bottom

底部坐标

### editObject.canCopy()

能否复制,

实际上也就是判断是否存在选区

### editObject.canPaste()

能否粘贴

### editObject.canRedo()

能否重做

### editObject.canUndo()

能否撤消

### editObject.capture

是否捕获全局鼠标消息

### editObject.className

运行时类�?
### editObject.clear()

清除选中文本

### editObject.close()

关闭控件�?
### editObject.cls

设计时类�?
### editObject.color

获取或修改字体颜色数�?
### editObject.copy()

复制

### editObject.cut()

剪切

### editObject.deselect()

取消选定

### editObject.disableInputMethod()

在此控件中关闭输入法, 仅支持英文输�?
### editObject.disabled

控件时否禁用

### editObject.disabledText

当指定文本时，禁用此控件并显示指定文本�?
指定�?null 时，启用此控件并恢复控件之前的正常文本�?
### editObject.dump(变量)

显示变量的�?支持多参�?
注意仅显示普通table,string,number等类型的�?不显示函数等

### editObject.enablePopMenu()

```aardio aardio
editObject.enablePopMenu(function(){
    return {
        { /*分隔�?/ };
        { "自定义菜单项";  function(id){
            /*enablePopMenu 用于启用文本框的右键菜单�?可选指定要增加的菜单配置表（或返回菜单配置表的函数）作为参数�?菜单配置表将作为参数传给 win.ui.popmenu 对象�?addTable 函数�?格式请查看该函数说明函数�?调用此函数必须事先引�?win.ui.menu �?/
        }; !owner.canCopy() ? 1/*_MF_GRAYED*/ : 0};
    }
})

```

### editObject.font

控件字体（LOGFONT 结构体）�?
注意获取该属性总是返回新的 LOGFONT 对象�?
修改返回字体并不会更新控件字体，

除非重新赋值�?
建议尽量优先使用 getFont �?setFont 函数�?
以增强代码可读�?
字体会根据控件设置自动处�?DPI 缩放，不需要事先缩放字体大�?
### editObject.getClientRect()

控件文本客户区块位置(::RECT结构�?

[返回对象:rectObject](../../../global/_.html#rectObject)

### editObject.getFont()

返回控件 LOGFONT 字体�?
返回对象�?h 值会按控件的 DPI 缩放设置自动还原为缩放前大小�?
[返回对象:logfontObject](#logfontObject)

### editObject.getFont(true)

返回控件 LOGFONT 字体�?
返回对象�?h 值为字体实际大小，不会按控件 DPI 设置还原�?
返回字体会设�?noScale 属性为 true,

使用控件�?setFont 函数或赋�?font 属性时�?
noScale 属性为 true 的字体同样不会进行自�?DPI 缩放

[返回对象:logfontObject](#logfontObject)

### editObject.getLength()

获取文本长度

注意是按字符计数，而不是按字节计数

### editObject.getParent()

返回父窗�?
[返回对象:staticObject](static.html#staticObject)

### editObject.getPos()

返回相对坐标,�?�?
x,y,cx,cy=win.getPos(hwnd)

### editObject.getRect()

控件区块位置(::RECT结构�?

### editObject.getRect(true)

控件屏幕区块位置(::RECT结构�?

### editObject.getRoot()

获取顶层父窗口，这个函数会查�?orphanWindow 的父窗口

### editObject.getsel()

获取选区起始位置,结束位置

选区包含起始与结束位置的字符，首字符位置�?

开始位置在指定的字符前�?结束位置表示指定的字符后�?
只有一个返回值时表示无选区,并表示输入光标在指定字符后面

返回0表示输入光标在最前面,并且无选区

### editObject.hScroll()

滚动到右�?
### editObject.hScroll(\_SB)

滚动横向滚动�?
### editObject.height

高度

### editObject.hide

当前控件窗口是否隐藏�?
仅检查当前窗口的可见性样式（窗口 是否移除�?\_WS\_VISIBLE 样式）�?
不考虑父窗口是否可见，不考虑是否被其他窗口遮挡�?
如果需要同时判断父窗口的可见性，应改�?win.isVisible 函数�?
### editObject.hwnd

控件句柄

### editObject.id

控件ID

### editObject.inflateClientRect(dx,dy)

正数增大,负数缩小文本客户�?
文本框必须在设计时指定为多行

在文本框改变大小必须重新设置

### editObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/)

使窗口绘图区无效

### editObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/,0)

使窗口绘图区无效

不刷新背�?
### editObject.isDialogMessage

```aardio aardio
editObject.isDialogMessage = function(hParent,msg){/*在控件范围内替代父窗口的 isDialogMessage�?可用于在控件范围内屏蔽对话框快捷键�?可用于禁�?tab 控制键的多行文本框支持按 tab 输入制表�?/}

```

### editObject.left

左侧坐标

### editObject.limit

字符数限�?注意不是以字节为单位,

此限制主要用于限制用户输�?对读写text属性无�?

如果设为0，单行文本框指定�?x7FFFFFFE，多行文本框指定�?1

如果用于限制log,print等函数输出字符数�?值不能设置过大或设为0、负数等

### editObject.lineCount

获取行数

### editObject.lineFromChar()

不指定参数则返回当前�?
### editObject.lineFromChar(指定位置)

返回指定位置行数

### editObject.lineLength(指定行号)

返回指定行字符数

省略参数表示当前�?小于0表示自尾部倒数到指定行,-1表示最后一�?
### editObject.lineScroll(滚动到指定行)

滚动条移动到指定�?
如果不指定参数则滚动到最后一�?
### editObject.lineSel(行号,替换文本)

选择指定的行的全部文�?

行号�?1时表示选取最后一�?

可选使用参数@2指定一个字符串用于替换该行文本

### editObject.lineText(指定行号)

获取指定行文�?
错误行号返回null空�?
省略参数表示当前�?小于0表示自尾部倒数到指定行,-1表示最后一�?
### editObject.lineToChar()

获取当前选定行首字符位置

### editObject.lineToChar(指定行号)

获取指定行首字符位置

省略参数表示当前�?小于0表示自尾部倒数到指定行,-1表示最后一�?
### editObject.lines(忽略空白)

```aardio aardio
for line in editObject.lines(true){
    /*遍历所有文本行,
如果迭代器参数为true则清除每行首尾空�?并忽略空�?/
}

```

### editObject.load()

自参�?@1 指定的文件路径加载文本�?
### editObject.log( ,'\\r\\n' )

追加字符串到文本�?可输入多个参�?
如果超出limit属性设定的字符数限制则移除头部多余的字�?
为提升性能,limit不可过大

### editObject.modified

文本内容是否已修改，可修改此属性�?
修改 text 属性、以及调�?log,print 等函数不会自动变更此属性�?
用户输入、selText 变更�?appendTexxt,appendLink 调用都会变更此属性为 true�?
### editObject.modifyStyle(remove,add,swpFlags)

修改窗口样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### editObject.modifyStyleEx(remove,add,swpFlags)

修改窗口扩展样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS\_EX_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS\_EX_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### editObject.onCancel()

```aardio aardio
editObject.onCancel = function(){
    /*当前已按下ESC,返回true阻止默认事件*/
    return true;
}

```

### editObject.onChange()

```aardio aardio
editObject.onChange = function(){
    if(owner.onModified)owner.onModified(true);

    owner.validateText("<\d+\.\d\d>|<\d+\.\d>|<\d+\.>|<\d+>"
        ,"请输入金额，小数点后不能超过 2 �?");

    /*响应事件，文本内容已变更�?edit 控件启用多行时用 text 属性赋值文本不会触发此事件�?log,print 函数调用也是基于修改 text 属性实现，也不会触发此事件�?�?appendText,selText 修改插入点文本的调用会触发此事件�?/
}

```

### editObject.onFocusGot()

```aardio aardio
editObject.onFocusGot = function(){
    /*响应事件，文本框已获得输入焦�?/
}

```

### editObject.onFocusLost()

```aardio aardio
editObject.onFocusLost = function(){
    /*响应事件，文本框已失去输入焦�?/
}

```

### editObject.onModified

```aardio aardio
editObject.onModified = function(modified){
    /*使用代码变更 modified 属性后触发此事�?
用户编辑文本导致变更 modified 属性不会触发此事件�?可在 onChange 事件内主动调用此事件*/
}

```

### editObject.onOk()

```aardio aardio
editObject.onOk = function(){
    /*当前已按下回�?返回true阻止默认事件*/
    return true;
}

```

### editObject.orphanWindow(transparent,hwndBuddy,borderless)

创建悬浮窗口�?
悬浮窗口是模仿子窗口外观效果的独立窗口，父窗口可自动调整子窗口到设定位置�?
可选参�?@transparent �?true 则转换为分层透明窗口�?
可选利�?@hwndBuddy 参数指定外部进程窗口句柄的并附加在内部控件上以实现相同的效果�?
伙伴窗口总是会保持在悬浮窗口前面，并保持相同的大小、位置�?
可重复调用此函数更换伙伴窗口，旧的伙伴窗口必须自行关闭�?
可选指�?@borderless 参数 �?true 以移�?@hwndBuddy 的窗口边框�?
### editObject.padding

文本边距

应通过 setPadding 函数设置该�?
### editObject.passwordChar

指定隐藏密码的占位字�?该字符使用UTF-16编码,

例如指定�?\*'u隐藏密码,指定为null正常显示文本

### editObject.paste()

粘贴

### editObject.postMessage(msg,wParam,lParam)

投递窗口消息到消息队列�?
此函数用法请参�?::User32.PostMessage

### editObject.preadjust

```aardio aardio
editObject.preadjust = function( cx,cy,wParam ) {
    /*窗口缩放后重绘前、触�?adjust 事件之前触发此事件�?所�?win.form 创建的窗体和控件都支持此事件,
�?adjust 事件不同，对 preadjust 重复赋值则覆盖而不是追加事件�?
cx 参数为窗口宽�?cy 参数为窗口高�?
wParam �?_WM_SIZE 消息参数�?/
};

```

### editObject.print(...)

将多个参数转换为字符�?

并使用制表符分隔各参数追加到文本尾部

并追加换�?
如果超出limit属性设定的字符数限制则移除头部多余的字�?
为提升性能,limit不可过大

对于table对象,aardio会序列化为文本然后输�?

如果当前已经导入了web.json，则自动转换为json后输�?

可以用于调试代码显示变量的�?
### editObject.printf(...)

将多个参数调用string.format格式化后追加到文本尾�?
并追加换�?
### editObject.publish("字符串参�?,)

在窗口所在界面线程发布消�?

运行界面线程所有所有调用subscribe函数订阅此消息的函数,

可添加任意个触发参数

### editObject.readonly

是否只读

只读时禁止编�?
### editObject.redo()

重做

### editObject.redraw()

刷新

### editObject.reloadScale()

按设计时位置参数、重新调整控件位置以适应窗口当前缩放比例�?
父窗口缩放时会自动执行此操作�?
默认在启动窗口消息循环时会自适应调整所有控件�?
所以在启动消息循环前添加控件不必调用此函数�?
### editObject.resize(宽度,高度)

如果指定了参数则调整窗口大小,

无论是否实际调整窗口大小,发�?\_WM\_SIZE 消息给窗�?
### editObject.right

右侧坐标

### editObject.save()

保存控件文本到参�?@1 指定的文件路径�?
### editObject.saveScale()

根据控件当前位置、缩放比例，更新控件的设计时位置参数�?
以避免下次窗口缩放自适应调整控件当前位置更改被清除，

控件所有调整位置的属性或成员函数已自动调用此函数�?
### editObject.scrollCaret()

滚动到光标处

### editObject.selLine

获取或设置当前行,

光标移动到该行开始处,并且滚动到该�?

设为-1跳转到最后一�?
### editObject.selText

获取或替换选区文本

### editObject.selectAll()

全�?
### editObject.sendMessage(msg,wParam,lParam)

发送窗口消�?
此函数用法请参�?::User32.SendMessage

### editObject.setClientRect(RECT区块)

参数为指定文本客户区的RECT结构�?
文本框必须在设计时指定为多行

在文本框改变大小必须重新设置

### editObject.setCueBannerText

指定单行文本框文本为空时的显示的默认提示文本

### editObject.setCueBannerText("提示文本",是否一直显�?

指定单行文本框默认提示文本�?
参数 @1 必须是字符串�?
参数 @2 可省略，默认仅失去焦点时显示�?
XP 系统不支持此函数、但调用不报错�?
注意 plus 控件提供支持XP系统�?setCueBannerText 函数

### editObject.setFocus

设置焦点,可指定选区参数

### editObject.setFocus()

设置焦点到文本框尾部

### editObject.setFocus(0)

设置焦点到文本框的指定位�?
### editObject.setFocus(0,-1)

全选并设置焦点

### editObject.setFont(指定字体)

指定 LOGFONT 字体对象,或逻辑字体句柄

如果不指�?point 值并指定 h 值，字体会按控件�?DPI 缩放设置自动缩放�?
### editObject.setFont(混入字体属�?

```aardio aardio
editObject.setFont(h=-12;name="Tahoma");

```

### editObject.setPadding(�?�?�?�?

设置文本边距，所有参数都可以省略�?
文本框必须在设计时指定为多行�?
在文本框改变大小后仍然可以保持此边距�?
边距默认应设置缩放前的原始�?
如果参数�?@5 �?true 则边距应为当�?DPI 缩放后的�?
### editObject.setParent(控件对象)

改变父窗�?
### editObject.setPos(x坐标,y坐标,�?�?插入位置,参数)

调整窗口位置或排�?所有参数可�?
同时指定x,y坐标则移动位�?
同时指定宽高则改变大�?
指定插入位置(句柄或\_HWND前缀常量)则调整Z�?
### editObject.setRect(rc)

设置控件区块位置(::RECT结构�?

### editObject.setRect(rc,true)

设置控件屏幕区块位置(::RECT结构�?

### editObject.setRedraw(false)

禁止重绘

### editObject.setRedraw(true)

恢复重绘

### editObject.setsel(当前位置)

无选区,

移动光标到指定位置的字符后面

### editObject.setsel(起始位置,结束位置)

设置选区,以字符为单位

1为首字符，选区包含起始与结束位�?
如果结束位置小于开始位�?自动交换参数位置

### editObject.show(true)

显示控件

### editObject.showBalloonTip

显示气泡提示,

建议直接调用showInfoTip，showWarningTip �?showErrorTip

### editObject.showBalloonTip(text)

在输入光标处显示汽泡提示,

@text参数指定文本

### editObject.showBalloonTip(title,text,icon)

在输入光标处显示汽泡提示,

@title参数指定标题,

@text参数指定文本,

icon指定图标句柄，可省略

### editObject.showErrorTip

在输入光标处显示汽泡提示,使用错误图标

### editObject.showErrorTip(text)

在输入光标处显示汽泡提示,使用错误图标,

@text参数指定文本

### editObject.showErrorTip(title,text,large)

在输入光标处显示汽泡提示,使用错误图标,

@title参数指定标题,

@text参数指定文本,

large指定是否使用大图标，可省�?
### editObject.showInfoTip

在输入光标处显示汽泡提示

### editObject.showInfoTip(text)

在输入光标处显示汽泡提示,使用提示信息图标,

@text参数指定文本

### editObject.showInfoTip(title,text,large)

在输入光标处显示汽泡提示,使用提示信息图标,

@title参数指定标题,

@text参数指定文本,

large指定是否使用大图标，可省�?
### editObject.showWarningTip

在输入光标处显示汽泡提示,使用警告图标

### editObject.showWarningTip(text)

在输入光标处显示汽泡提示,使用警告图标,

@text参数指定文本

### editObject.showWarningTip(title,text,large)

在输入光标处显示汽泡提示,使用警告图标,

@title参数指定标题,

@text参数指定文本,

large指定是否使用大图标，可省�?
### editObject.tabNext()

[返回对象:staticObject](static.html#staticObject)

### editObject.tabNext(移动焦点,是否反向)

获取下一个支持tab控制焦点的控�?
参数@1为true会自动移动焦点到该控�?
参数@2为true则获取上一个控�?否则获取下一个控�?
### editObject.text

获取或写入编辑控件文本属性�?
可写�?UTF8 �?UTF16 字符串，写入 null 值转换为空字符串�?
其他类型值用 tostring 转为字符串后写入�?
注意 edit 控件使用'\\r\

'表示换行,�?richedit 控件则使�?\

'表示换行�?
用双引号或反引号包含字符串赋值时换行会自动将换行解析�?\

'�?
用块注释赋值为字符串时会自动将换行规范化解析为'\\r\

'�?
例如 winform.edit.txt = /\*文本

第二行文本\*/

### editObject.theme

外观主题,例如

winform.button.theme = "Explorer"

winform.button.theme = false

### editObject.threadCallable()

开启此控件的跨线程调用功能

### editObject.top

顶部坐标

### editObject.translateAccelerator(msg)

```aardio aardio
editObject.translateAccelerator = function(msg){
    var vk = msg.wParam;
    if( (vk == 0x9/*_VK_TAB*/ ) || (vk = 0xD/*_VK_RETURN*/) ){
        if( msg.message == 0x100/*_WM_KEYDOWN*/) {
            owner.tabNext(true);
            return true;/*在此事件中可拦截键盘消息并自定义快捷�?tabNext函数切换到下一个支持tab控制键的控件
如果这是一个快捷键返回true以取消该消息的默认行�?/
        }
    }
}

```

### editObject.translateCommand()

允许转发转发子窗口的命令（\_WM\_COMMAND）与通知（\_WM\_NOTIFY）消息，

避免子窗�?oncommand，onnotify 等回调失效�?
同时会处理子窗口�?\_WM\_CTLCOLORSTATIC 等消息，

以避免部分外观属性失�?
### editObject.undo()

撤消

### editObject.update()

重绘invalidate函数指定的区�?
### editObject.vScroll()

滚动到底�?
### editObject.vScroll(\_SB)

滚动竖向滚动�?
### editObject.valid

窗口是否有效�?
窗口未关闭返�?true �?
窗口已关闭或正在关闭返回 false

### editObject.validateText

校验输入文本�?
全部文本完全符合要求返回 true，否则返�?false�?
可在 onChange 事件内调用此函数实时校验输入�?
如果需要限制数字，

更简单的方法是在窗体设计器中设置控件的『限制数字』属性为 true�?
也就是指定控件的创建参数 num 的值为 true�?
### editObject.validateText(校验输入函数,错误信息)

调用参数 @1 指定的函数校验控件的文本属性，

该函数必须自参数中接收当前文本并返回合法文本�?null�?
然后将文本设为符合合法的文本，如果校验函数返�?null 设为空字符串�?
如果修改了文本且指定了字符串参数 @2 ，则在控件内用气泡提示显示参�?@2 指定的错误信息，

并且将焦点切换到该控件，然后将输入光标设置到文本尾部�?
### editObject.validateText(模式�?错误信息)

用字符串参数 @1 指定的模式串校验控件的文本属性�?
将文本设为符合匹配的文本，如果找不到匹配文本设为空字符串�?
如果修改了文本且指定了字符串参数 @2 �?
则在控件内用气泡提示显示参数 @2 指定的错误信息，

并且将焦点切换到该控件，然后将输入光标设置到文本尾部�?
### editObject.validateText(模式�?错误标题,错误信息)

用字符串参数 @1 指定的模式串校验控件的文本属性�?
将文本设为符合匹配的文本，如果找不到匹配文本设为空字符串�?
如果修改了文本且指定了字符串参数 @2,@3 �?
则在控件内用气泡提示显示参数 @2,@3 指定的错误信息，

并且将焦点切换到该控件，然后将输入光标设置到文本尾部�?
### editObject.validateText(限制金额示例,错误标题,错误信息)

```aardio aardio
editObject.validateText("<\d+\.\d\d>|<\d+\.\d>|<\d+\.>|<\d+>",
    "不能接受的字�?,"只能在此输入金额，小数点后不能超�?2 �?")

```

### editObject.width

宽度

### editObject.wrap

是否启用自动换行,仅richedit支持

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/win/ui/ctrl/edit.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/win/ui/ctrl/edit.md')

