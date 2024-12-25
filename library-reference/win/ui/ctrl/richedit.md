[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# win.ui.ctrl.richedit 库模块帮助文�?
必读文档

## 设置文本样式

### 使用 COM 接口实现�?TOM 文本对象设置样式

以下是一个简单示例：

```
textDoc = winform.richedit.createTextDocument()
textDoc.Selection.Text = "这是红色加粗的文�?
textDoc.Selection.Font.ForeColor = gdi.RGB(255,0,0)  // 红色
textDoc.Selection.Font.Bold = textDoc.tomTrue  // 加粗

```

[TOM 文档](https://learn.microsoft.com/zh-cn/windows/win32/controls/text-object-model?redirectedfrom=MSDN)

### 使用 CHARFORMAT2 结构体设置样�?
以下函数会用�?CHARFORMAT2（这里指的是 win.ui.ctrl.CHARFORMAT2 类） 结构体�?
- appendText 支持任意个文本参数与任意�?CHARFORMAT2 参数，如果修改了样式则函数返回前恢复默认样式
- setSelCharformat 修改当前选区或插入点样式，传入指�?CHARFORMAT2 部分字段的表即可�?- getSelCharformat 获取当前选区或插入点样式，返�?CHARFORMAT2
- setCharformat 修改样式 ，传入指�?CHARFORMAT2 部分字段的表即可�?- getCharformat 获取样式，返�?CHARFORMAT2
- setLink 设置超链接样�?- appendLink 追加超链�?
设置样式的函数可直接指定普通表参数（不需要指定全�?CHARFORMAT2 字段），
aardio 会自动将这些表转换为完整�?CHARFORMAT2 结构体�?并且会自动设�?mask 字段的掩码�?�?aardio 会自动设置值，所以这个最复杂的部分可以不用管了�?所以只要字段名写对就可以了�?
CHARFORMAT2 有以下字�?
- backColor: 背景颜色，GDI 颜色格式�?0xBBGGRR ）�?- textColor: 字体颜色，GDI 颜色格式�?0xBBGGRR ）�?- faceName: 字体�?- bold = 是否粗体，仅用于写入样式。\\n设置了这个值会在应用样式前自动修改 weight 属性�?- underline = 是否粗体，仅用于写入样式�?- italic = 是否斜体，仅用于写入样式�?- strikeout = 是否显示删除线，仅用于写入样式�?
- disabled = 偏移一个像素，仅用于写入样式�?- protected = 保护文本，修改时触发 onProtected 事件。\\n仅用于写入样式，仅用于设置全部文本，不适用选区�?- weight: 字体重量，一般不要改，改 bold 即可
- spacing: 字体间距
- effects: 效果
- yHeight: 字体大小，以 twips 为单�?- point: 字体大小，以 pt 为单位。设置样式时指定 point 会在应用样式前自动修�?yHeight 的值�?- yOffset: 偏移
- charSet: 字符�?- pitchAndFamily: 字体�?- lcid: 区域ID
- underlineType: 下划线类�?- mask 掩码，这个一般不用管
- getFont() 返回LOGFONT对象

注意修改字体大小请在窗体显示并且 DPI 初始化缩放完成以后再设置，不然会被重复放大�?如果要在窗体显示前设置，请在设置字体大小前主动调�?winform.enableDpiScaling("init");

## 参考文档：

[https://learn.microsoft.com/en-us/windows/win32/controls/about-rich-edit-controls](https://learn.microsoft.com/en-us/windows/win32/controls/about-rich-edit-controls) [https://github.com/MicrosoftDocs/win32/blob/docs/desktop-src/Controls/about-rich-edit-controls.md](https://github.com/MicrosoftDocs/win32/blob/docs/desktop-src/Controls/about-rich-edit-controls.md) [https://learn.microsoft.com/zh-cn/windows/win32/api/richedit/ns-richedit-charformatw](https://learn.microsoft.com/zh-cn/windows/win32/api/richedit/ns-richedit-charformatw) [https://learn.microsoft.com/zh-cn/windows/win32/api/richedit/ns-richedit-charformat2w](https://learn.microsoft.com/zh-cn/windows/win32/api/richedit/ns-richedit-charformat2w)

API 常量�?aardio 里需要在前面加一个下划线，然后利�?IDE 的自动完成可自动转换为实际的常量值�?
## win.ui.ctrl 成员列表

### win.ui.ctrl.CHARFORMAT2()

用于创建 richedit 支持�?CHARFORMAT2 结构体�?
因为 richedit 提供的函数可将样式表参数自动转换为此结构�?
所以一般不需要手动创建此结构体�?
注意 aardio 中的 CHARFORMAT2 结构体字段命名与 MSDN 有微小差别�?
[返回对象:charformat2Object](#charformat2Object)

### win.ui.ctrl.richedit

多功能文本框控件支持�?
### win.ui.ctrl.richedit()

多功能文本框控件

[返回对象:richeditObject](#richeditObject)

## richeditObject 成员列表

### richeditObject.\_defWindowProc(hwnd,message,wParam,lParam)

用于�?wndproc 回调中提前调用默认消息回调函�?

所有窗口和控件定义�?wndproc 回调以后会自动创建这个函�?

调用此函数以�?wndproc 必须指定�?null 返回�?

以避免再次重复调用默认回调函�?
### richeditObject.\_parentForm

创建该控件的父窗口（win.form对象�?

设计时窗体容器是所有拖放在窗体上的控件�?\_parentForm,

即使窗口移除子窗口样式、更改父子关系，或以 orphanWindow显示,

控件�?\_parentForm 始终都不会改�?
[返回对象:winform](../_.html#winform)

### richeditObject.addCtrl(tParam)

```aardio aardio
richeditObject.addCtrl(
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

### richeditObject.adjust

```aardio aardio
richeditObject.adjust = function( cx,cy,wParam ) {
    /*窗口缩放时会自动触发此函数�?cx 参数为窗口宽�?cy 参数为窗口高�?
wParam 参数请参�?_WM_SIZE 消息参数说明,一般不用管�?
所�?win.form 创建的窗体和控件都支持此事件,
重复赋值只会追加而不会覆盖此事件�?一般不建议添加一�?wndproc 仅仅是为了处�? _WM_SIZE 消息�?定义 adjust 事件是更好的选择�?
可主动调用此事件,省略参数�?cx,cy 参数默认设为窗口大小*/
};

```

### richeditObject.appendLink

在文本尾部追加超链接�?
如果未定�?onHyperlink 事件�?
则添加默�?onHyperlink 调用 raw.execute 函数打开链接�?
此函数会自动禁用自动识别超链接功能，但不会取消之前自动识别的超链接�?
### richeditObject.appendLink(title,href,charFormat2)

在文本尾部追加超链接�?
参数 @title 指定显示文本�?
参数 @href 指定超链接或文件路径�?
参数 @charFormat2 可选指定包�?win.ui.ctrl.CHARFORMAT2 部分字段的表

默认会通过插入位置获取超链接，

如果超链接位置改变而获取失败，则通过 title 指定显示名称获取链接�?
### richeditObject.appendText

追加文本并移动光标插入点到文本尾部�?
用法细节请参�?richedit 库函数文档�?
### richeditObject.appendText(追加文本-..)

追加文本并移动光标插入点到文本尾部�?
可指定零个、或多个参数，参数可以是字符串、buffer、数值�?
如果参数是表对象，则将该表作�?setSelCharformat 的参数修改插入点样式�?
如果修改字体大小请在窗体显示 DPI 缩放以后设置�?
如果传入了样式参数，在函数调用结束总是会恢复为默认样式�?
传入其他类型参数会抛出异常�?
函数返回插入文本以后控件的文本总长度�?
### richeditObject.bgcolor

获取或修改背景颜色、数�?
### richeditObject.bottom

底部坐标

### richeditObject.canCopy()

能否复制

### richeditObject.canPaste()

能否粘贴

### richeditObject.canRedo()

能否重做

### richeditObject.canUndo()

能否撤消

### richeditObject.capture

是否捕获全局鼠标消息

### richeditObject.className

运行时类�?
### richeditObject.clear()

清除选中文本

### richeditObject.close()

关闭控件�?
### richeditObject.cls

设计时类�?
### richeditObject.color

取或修改字体颜色、数�?
### richeditObject.copy()

复制选区�?
如果要复制全�?RTF 文档�?
可用 win.clip.data("Rich Text Format") 复制

### richeditObject.createTextDocument()

返回 COM 接口�?[TOM 文本对象](https://learn.microsoft.com/zh-cn/windows/win32/controls/text-object-model?redirectedfrom=MSDN)

[返回对象:TextDocumentObject](#TextDocumentObject)

### richeditObject.cut()

剪切选区

### richeditObject.deselect()

取消选定

### richeditObject.disableInputMethod()

在此控件中关闭输入法, 仅支持英文输�?
### richeditObject.disabled

控件时否可见

### richeditObject.disabledText

当指定文本时，禁用此控件并显示指定文本�?
指定�?null 时，启用此控件并恢复控件之前的正常文本�?
### richeditObject.dump(变量)

显示变量的�?支持多参�?
注意仅显示普通table,string,number等类型的�?不显示函数等

### richeditObject.enablePopMenu()

```aardio aardio
richeditObject.enablePopMenu(function(){
    return {
        { /*分隔�?/ };
        { "自定义菜单项";  function(id){
            /*enablePopMenu 用于启用文本框的右键菜单�?可选指定要增加的菜单配置表（或返回菜单配置表的函数）作为参数�?菜单配置表将作为参数传给 win.ui.popmenu 对象�?addTable 函数�?格式请查看该函数说明*/
        }; !owner.canCopy() ? 1/*_MF_GRAYED*/ : 0};
    }
})

```

### richeditObject.findText

查找文本

### richeditObject.findText(查找字符�?选项,开始位�?结束位置)

查找

选项可使�?win.dlg.findReplace 对象�?flags 属�?

不指定查找范围时,aardio 根据选区自动确定下次替换的范�?
替换完全部文本会重新重新设置查找范围为全部文�?
此函数返�?个数值，表示查找到的字符串起始、结束位�?
如果参数中未指定查找位置,会自动选中查找到的字符�?
### richeditObject.font

控件字体（LOGFONT 结构体）�?
注意获取该属性总是返回新的 LOGFONT 对象�?
修改返回字体并不会更新控件字体，

除非重新赋值�?
建议尽量优先使用 getFont �?setFont 函数�?
以增强代码可读�?
字体会根据控件设置自动处�?DPI 缩放，不需要事先缩放字体大�?
### richeditObject.getCharformat()

[返回对象:charformat2Object](#charformat2Object)

### richeditObject.getCharformat(mask)

返回 win.ui.ctrl.CHARFORMAT2 结构体�?
参数 @mask 指定获取字段掩码,省略获取全部�?
### richeditObject.getClientRect()

控件客户区块位置(::RECT结构�?

[返回对象:rectObject](../../../global/_.html#rectObject)

### richeditObject.getFont()

返回控件 LOGFONT 字体�?
返回对象�?h 值会按控件的 DPI 缩放设置自动还原为缩放前大小�?
[返回对象:logfontObject](#logfontObject)

### richeditObject.getFont(true)

返回控件 LOGFONT 字体�?
返回对象�?h 值为字体实际大小，不会按控件 DPI 设置还原�?
返回字体会设�?noScale 属性为 true,

使用控件�?setFont 函数或赋�?font 属性时�?
noScale 属性为 true 的字体同样不会进行自�?DPI 缩放

[返回对象:logfontObject](#logfontObject)

### richeditObject.getLength()

获取文本长度

注意是按字符计数，而不是按字节计数

### richeditObject.getParent()

返回父窗�?
[返回对象:staticObject](static.html#staticObject)

### richeditObject.getPos()

返回相对坐标,�?�?
x,y,cx,cy=win.getPos(hwnd)

### richeditObject.getRect()

控件区块位置(::RECT结构�?

### richeditObject.getRect(true)

控件屏幕区块位置(::RECT结构�?

### richeditObject.getRoot()

获取顶层父窗口，这个函数会查�?orphanWindow 的父窗口

### richeditObject.getSelCharformat()

[返回对象:charformat2Object](#charformat2Object)

### richeditObject.getSelCharformat(mask)

返回选区 win.ui.ctrl.CHARFORMAT2 结构体�?
参数 @mask 指定获取字段掩码,省略获取全部�?
### richeditObject.getsel()

获取选区起始位置,结束位置

选区包含起始与结束位置的字符，首字符位置�?

开始位置在指定的字符前�?结束位置表示指定的字符后�?
只有一个返回值时表示无选区,并表示输入光标在指定字符后面

返回0表示输入光标在最前面,并且无选区

### richeditObject.hScroll()

滚动到右�?
### richeditObject.hScroll(\_SB)

滚动横向滚动�?
### richeditObject.height

高度

### richeditObject.hide

当前控件窗口是否隐藏�?
仅检查当前窗口的可见性样式（窗口 是否移除�?\_WS\_VISIBLE 样式）�?
不考虑父窗口是否可见，不考虑是否被其他窗口遮挡�?
如果需要同时判断父窗口的可见性，应改�?win.isVisible 函数�?
### richeditObject.hwnd

控件句柄

### richeditObject.id

控件ID

### richeditObject.inflateClientRect(dx,dy)

正数增大,负数缩小文本客户�?
文本框必须在设计时指定为多行

在文本框改变大小必须重新设置

### richeditObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/)

使窗口绘图区无效

### richeditObject.invalidate(/\*可选使�?:RECT()对象指定客户区\*/,0)

使窗口绘图区无效

不刷新背�?
### richeditObject.isDialogMessage

```aardio aardio
richeditObject.isDialogMessage = function(hParent,msg){/*在控件范围内替代父窗口的 isDialogMessage�?可用于在控件范围内屏蔽对话框快捷键�?可用于禁�?tab 控制键的多行文本框支持按 tab 输入制表�?/}

```

### richeditObject.langOptions

设置输入和远东语言选项

选项为数�?使用\_IMF\_前缀常量表示

### richeditObject.left

左侧坐标

### richeditObject.limit

字符数限�?
### richeditObject.lineCount

获取行数

### richeditObject.lineFromChar()

不指定参数则返回当前�?
### richeditObject.lineFromChar(指定位置)

返回指定位置行数

### richeditObject.lineLength(指定行号)

返回指定行字符数

省略参数表示当前�?小于0表示自尾部倒数到指定行,-1表示最后一�?
### richeditObject.lineScroll(滚动到指定行)

滚动条移动到指定�?
如果不指定参数则滚动到最后一�?
### richeditObject.lineSel(行号,替换文本)

选择指定的行的全部文�?

行号�?1时表示选取最后一�?

可选使用参数@2指定一个字符串用于替换该行文本

### richeditObject.lineText()

不指定行号参�?则获取当前行文本

### richeditObject.lineText(指定行号)

获取指定行文�?
省略参数表示当前�?小于0表示自尾部倒数到指定行,-1表示最后一�?
### richeditObject.lineToChar(指定行号)

获取指定行首字符位置

省略参数表示当前�?小于0表示自尾部倒数到指定行,-1表示最后一�?
### richeditObject.lines(忽略空白)

```aardio aardio
for line in richeditObject.lines(true){
    /*遍历所有文本行,
如果迭代器参数为true则清除每行首尾空�?并忽略空�?/
}

```

### richeditObject.link

控件是否自动识别超链接�?
启用此属性会重新设置控件文本内容并丢失选区样式�?
如果未定�?onHyperlink 事件�?
则添加默�?onHyperlink 调用 raw.execute 函数打开链接�?
禁用此属性不会重置文本内容，之前识别的超链接不会失效�?
### richeditObject.load()

自参�?@1 指定的文件路径加载文本�?
如果文件后缀�?.rtf 则加�?RTF 格式文本�?
此函数内部调�?streamIn 函数�?
### richeditObject.log( ,'\\r\\n' )

追加字符串到文本�?可输入多个参�?
如果超出limit属性设定的字符数限制则移除头部多余的字�?
为提升性能,limit不可过大

### richeditObject.modified

文本内容是否已修改�?
修改 text 属性、以及调�?log,print 等函数不会自动变更此属性�?
用户输入、selText 变更�?appendTexxt,appendLink 调用都会变更此属性为 true�?
### richeditObject.modifyEvent(移除通知,添加通知)

启用或禁用通知消息,返回EVENTMASK�?
### richeditObject.modifyStyle(remove,add,swpFlags)

修改窗口样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### richeditObject.modifyStyleEx(remove,add,swpFlags)

修改窗口扩展样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS\_EX_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS\_EX_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### richeditObject.onCancel()

```aardio aardio
richeditObject.onCancel = function(){
    /*当前已按下ESC,返回true阻止默认事件*/
    return true;
}

```

### richeditObject.onChange()

```aardio aardio
richeditObject.onChange = function(){
    if(owner.onModified)owner.onModified(true);

    owner.validateText("<\d+\.\d\d>|<\d+\.\d>|<\d+\.>|<\d+>"
        ,"请输入金额，小数点后不能超过 2 �?");

    /*响应事件，文本内容已变更�?对于 richedit 修改 text 属性赋值文本会触发此事件�?但可以通过 modified 属性判断是否由赋�?text 而触发�?*/
}

```

### richeditObject.onDpiFontChange

```aardio aardio
richeditObject.onDpiFontChange = function(f){
    return owner.setFont(f);/*自定义DPI字体缩放*/
};

```

### richeditObject.onFocusGot()

```aardio aardio
richeditObject.onFocusGot = function(){
    /*响应事件，文本框已获得输入焦�?/
}

```

### richeditObject.onFocusLost()

```aardio aardio
richeditObject.onFocusLost = function(){
    /*响应事件，文本框已失去输入焦�?/
}

```

### richeditObject.onHyperlink

```aardio aardio
richeditObject.onHyperlink =function(message,href){

    if( message = 0x202/*_WM_LBUTTONUP*/ ) {
        raw.execute(href);
    }
}

```

### richeditObject.onModified

```aardio aardio
richeditObject.onModified = function(modified){
    /*使用代码变更modified属性后触发此事�?
用户编辑文本导致变更modified属性不会触发此事件�?可在onChange事件内主动调用此事件*/
}

```

### richeditObject.onOk()

```aardio aardio
richeditObject.onOk = function(){
    /*当前已按下回�?返回true阻止默认事件*/
    return true;
}

```

### richeditObject.onProtected

```aardio aardio
richeditObject.onProtected = function(b,e,message){
    /*修改保护样式文本触发此事件�?b,e 为被修改的选区，message 为触发消息�?返回 true 禁止修改*/
    return true;
}

```

### richeditObject.orphanWindow(transparent,hwndBuddy,borderless)

创建悬浮窗口�?
悬浮窗口是模仿子窗口外观效果的独立窗口，父窗口可自动调整子窗口到设定位置�?
可选参�?@transparent �?true 则转换为分层透明窗口�?
可选利�?@hwndBuddy 参数指定外部进程窗口句柄的并附加在内部控件上以实现相同的效果�?
伙伴窗口总是会保持在悬浮窗口前面，并保持相同的大小、位置�?
可重复调用此函数更换伙伴窗口，旧的伙伴窗口必须自行关闭�?
可选指�?@borderless 参数 �?true 以移�?@hwndBuddy 的窗口边框�?
### richeditObject.padding

文本边距

应通过setPadding函数设置该�?
### richeditObject.passwordChar

指定隐藏密码的占位字�?该字符使用UTF-16编码,

例如指定�?\*'u隐藏密码,指定为null正常显示文本

### richeditObject.paste()

粘贴

### richeditObject.popMenu()

弹出右键菜单

### richeditObject.postMessage(msg,wParam,lParam)

投递窗口消息到消息队列�?
此函数用法请参�?::User32.PostMessage

### richeditObject.preadjust

```aardio aardio
richeditObject.preadjust = function( cx,cy,wParam ) {
    /*窗口缩放后重绘前、触�?adjust 事件之前触发此事件�?所�?win.form 创建的窗体和控件都支持此事件,
�?adjust 事件不同，对 preadjust 重复赋值则覆盖而不是追加事件�?
cx 参数为窗口宽�?cy 参数为窗口高�?
wParam �?_WM_SIZE 消息参数�?/
};

```

### richeditObject.print(...)

将多个参数转换为字符�?

并使用制表符分隔各参数追加到文本尾部

并追加换�?
对于table对象,aardio会序列化为文本然后输�?

如果当前已经导入了web.json，则自动转换为json后输�?

可以用于调试代码显示变量的�?
### richeditObject.printf(...)

将多个参数调用string.format格式化后追加到文本尾�?
并追加换�?
### richeditObject.publish("字符串参�?,)

在窗口所在界面线程发布消�?

运行界面线程所有所有调用subscribe函数订阅此消息的函数,

可添加任意个触发参数

### richeditObject.rangeText(起始位置,结束位置)

返回指定位置文本

1表示首字�?
### richeditObject.readonly

是否只读

只读时禁止编�?
### richeditObject.redo()

重做

### richeditObject.redraw()

刷新

### richeditObject.replaceAll

全部替换查找到的文本

### richeditObject.replaceAll(查找字符�?替换字符�?选项)

全部替换查找到的文本

选项可使用win.dlg.findReplace对象的flags属�?
### richeditObject.replaceText

替换替换文本

### richeditObject.replaceText(查找字符�?替换字符�?选项,开始位�?结束位置)

替换当前选区并查找下一个，

选项可使�?win.dlg.findReplace 对象�?flags 属�?

不指定查找范围时,aardio 根据选区自动确定下次替换的范�?
替换完全部文本会重新重新设置查找范围为全部文本，

此函数返�?个数值，表示下一个找到的字符串起始、结束位�?
### richeditObject.resize(宽度,高度)

如果指定了参数则调整窗口大小,

无论是否实际调整窗口大小,发�?\_WM\_SIZE 消息给窗�?
### richeditObject.right

右侧坐标

### richeditObject.rtf

获取或写�?RTF 格式文本�?
读写此属性会自动转换为调�?streamIn,streamOut 函数�?
### richeditObject.save()

保存控件文本到参�?@1 指定的文件路径�?
如果文件后缀�?.rtf 则保�?RTF 格式文本�?
此函数内部调�?streamOut 函数�?
### richeditObject.saveScale(scaleX,scaleY,dpiScaleX,dpiScaleY)

根据控件当前的运行时位置更新设计时大小\\如果控件允许自动缩放，窗口缩放时依据设计时大小按比例缩放

所有参数可省略,并且不建议写参数

### richeditObject.scrollCaret()

滚动到光标处

### richeditObject.selLine

获取或设置当前行,

光标移动到该行开始处,并且滚动到该�?

设为-1跳转到最后一�?
### richeditObject.selText

获取或写入选区文本

可写入UTF8或UTF16字符串，其他类型转为字符串写�?
### richeditObject.selectAll()

全�?
### richeditObject.sendMessage(msg,wParam,lParam)

发送窗口消�?
此函数用法请参�?::User32.SendMessage

### richeditObject.setCharformat

修改样式�?
如果修改字体大小请在窗体显示 DPI 缩放以后设置�?
用法细节请参�?richedit 库函数文档�?
### richeditObject.setCharformat(charformat2,wParam)

参数 @charformat2 使用 win.ui.ctrl.CHARFORMAT2 结构体设置文本样式，

可仅指定部分字段

wParam可省�?可选值参考EM\_SETCHARFORMAT消息。\\例如修改字体颜色可传�?{textColor=0x00ff00}

### richeditObject.setClientRect(RECT区块)

参数为指定文本客户区的RECT结构�?
文本框必须在设计时指定为多行

在文本框改变大小必须重新设置

### richeditObject.setFocus()

设置焦点

### richeditObject.setFont(指定字体)

指定 LOGFONT 字体对象,或逻辑字体句柄

如果不指�?point 值并指定 h 值，字体会按控件�?DPI 缩放设置自动缩放�?
### richeditObject.setFont(混入字体属�?

```aardio aardio
richeditObject.setFont(h=-12;name="Tahoma");

```

### richeditObject.setLink

设置当前选区为超链接�?
如果未定�?onHyperlink 事件�?
则添加默�?onHyperlink 调用 raw.execute 函数打开链接�?
此函数会自动禁用自动识别超链接功能，但不会取消之前自动识别的超链接�?
### richeditObject.setLink(href,charFormat2)

设置当前选区为超链接�?
参数 @href 指定超链接或文件路径�?
参数 @charFormat2 可选指定包�?win.ui.ctrl.CHARFORMAT2 部分字段的表

默认会通过插入位置获取超链接，

如果超链接位置改变而获取失败，则通过 title 指定显示名称获取链接

### richeditObject.setPadding(�?�?�?�?

设置文本边距

文本框必须在设计时指定为多行

在文本框改变大小后仍然可以保持此边距

### richeditObject.setParent(控件对象)

改变父窗�?
### richeditObject.setPos(x坐标,y坐标,�?�?插入位置,参数)

调整窗口位置或排�?所有参数可�?
同时指定x,y坐标则移动位�?
同时指定宽高则改变大�?
指定插入位置(句柄或\_HWND前缀常量)则调整Z�?
### richeditObject.setRect(rc)

设置控件区块位置(::RECT结构�?

### richeditObject.setRect(rc,true)

设置控件屏幕区块位置(::RECT结构�?

### richeditObject.setSelCharformat

设置选区样式�?
用法细节请参�?richedit 库函数文档�?
如果当前没有选区则修改插入点样式，新的样式仅在插入位置修改前有效�?
可调用控件的 setFocus,setsel 函数修改选区或光标插入位置�?
### richeditObject.setSelCharformat(charformat2)

参数 @charformat2 使用 win.ui.ctrl.CHARFORMAT2 结构体设置文本样式，

传入仅指定部分字段的表将自动转换�?CHARFORMAT2 结构体。\\例如修改字体颜色可传�?{textColor=0x00ff00}

### richeditObject.setSelCharformat(null)

将选区或光标插入点样式设为默认样式�?
### richeditObject.setsel(当前位置)

无选区,

移动光标到指定位置的字符后面

### richeditObject.setsel(起始位置,结束位置)

设置选区,以字符为单位

1为首字符，选区包含起始与结束位�?
如果结束位置小于开始位�?自动交换参数位置,

注意richedit实际以＼n换行,输入字符中的＼r＼n作为一个字符计�?
可以�?1表示文本尾部

### richeditObject.show(true)

显示控件

### richeditObject.streamIn

读入 RTF 文档或普通文�?
### richeditObject.streamIn(RTF文本)

加载字符串参�?@1 指定�?RTF 格式文本

### richeditObject.streamIn(格式,RTF文件路径)

读入 RTF 文档或普通文档，

格式参数默认�?\_SF\_RTF 用于读入 RTF 文档�?
指定�?\_SF\_TEXT 则读入普通文�?
### richeditObject.streamIn(格式,输入函数)

```aardio aardio
richeditObject.streamIn(,function(format,buf,len){
    return 0,file.readBuffer(buf,len);/*格式参数默认�?_SF_RTF，用于读�?RTF 文档�?指定�?_SF_TEXT 则读入普通文本�?成功读取文件回调函数应返�?0 与读取长度，
否则请返回错误代�?/
} )

```

### richeditObject.streamOut

输出 RTF 文档或普通文�?
### richeditObject.streamOut(格式)

直接返回 RTF 格式或普通文本�?
格式参数默认�?\_SF\_RTF 用于输出 RTF 文档�?
指定�?\_SF\_TEXT 则输出普通文�?
### richeditObject.streamOut(格式,RTF文件路径)

输出 RTF 文档或普通文档，

格式参数默认�?\_SF\_RTF 用于输出 RTF 文档�?
指定�?\_SF\_TEXT 则输出普通文�?
### richeditObject.streamOut(格式,输出函数)

```aardio aardio
richeditObject.streamOut(,function(format,buf,len){
    var ok,bytes = file.writeBuffer(buf,len);/*保存RTF文档*/
    return 0,bytes;
} )

```

### richeditObject.tabNext()

[返回对象:staticObject](static.html#staticObject)

### richeditObject.tabNext(移动焦点,是否反向)

获取下一个支持tab控制焦点的控�?
参数@1为true会自动移动焦点到该控�?
参数@2为true则获取上一个控�?否则获取下一个控�?
### richeditObject.text

获取或写入编辑控件文本属性�?
可写�?UTF8 �?UTF16 字符串，写入 null 值转换为空字符串�?
其他类型值用 tostring 转为字符串后写入�?
注意 edit 控件使用'\\r\

'表示换行,�?richedit 控件则使�?\

'表示换行�?
用双引号或反引号包含字符串赋值时换行会自动将换行解析�?\

'�?
例如 winform.richedit.txt = "文本

第二行文�?

### richeditObject.theme

外观主题,例如

winform.button.theme = "Explorer"

winform.button.theme = false

### richeditObject.threadCallable()

开启此控件的跨线程调用功能

### richeditObject.top

顶部坐标

### richeditObject.translateAccelerator(msg)

```aardio aardio
richeditObject.translateAccelerator = function(msg){
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

### richeditObject.translateCommand()

允许转发转发子窗口的命令（\_WM\_COMMAND）与通知（\_WM\_NOTIFY）消息，

避免子窗�?oncommand，onnotify 等回调失效�?
同时会处理子窗口�?\_WM\_CTLCOLORSTATIC 等消息，

以避免部分外观属性失�?
### richeditObject.undo()

撤消

### richeditObject.update()

重绘invalidate函数指定的区�?
### richeditObject.vScroll()

滚动到底�?
### richeditObject.vScroll(\_SB)

滚动竖向滚动�?
### richeditObject.valid

窗口是否有效�?
窗口未关闭返�?true �?
窗口已关闭或正在关闭返回 false

### richeditObject.validateText

校验输入文本�?
全部文本完全符合要求返回 true，否则返�?false�?
可在 onChange 事件内调用此函数实时校验输入�?
### richeditObject.validateText(校验输入函数,是否设置光标)

调用参数 @1 指定的函数校验控件的文本属性，

该函数必须自参数中接收当前文本并返回合法文本�?null�?
然后将文本设为符合合法的文本，如果校验函数返�?null 设为空字符串�?
如果修改了文本且指定了参�?@2 �?true，\\则将焦点切换到该控件，然后将输入光标设置到文本尾部�?
注意�?edit 控件可直接显示气泡提示，

richedit 无此功能可使用其他控件显示错误信息�?
### richeditObject.validateText(模式�?是否设置光标)

用字符串参数 @1 指定的模式串校验控件的文本属性�?
将文本设为符合匹配的文本，如果找不到匹配文本设为空字符串�?
如果修改了文本且指定了参�?@2 �?true，\\则将焦点切换到该控件，然后将输入光标设置到文本尾部�?
注意�?edit 控件可直接显示气泡提示，

richedit 无此功能可使用其他控件显示错误信息�?
### richeditObject.validateText(限制金额示例,是否设置光标)

```aardio aardio
richeditObject.validateText("<\d+\.\d\d>|<\d+\.\d>|<\d+\.>|<\d+>",true)

```

### richeditObject.width

宽度

### richeditObject.wrap

是否启用自动换行，仅 richedit 支持

### richeditObject.zoom

缩放比例，必须大�?1/32 并小�?32

Richedit 存在一�?BUG：如果不是左对齐,只要设置缩放 —�?包含中文就会偏移错乱,

所以右对齐或居中对齐后，自�?DPI 缩放将会更改为设置文本框默认字体,

这会导致局部字体样式被重置为默认字�?
## TextDocumentObject 成员列表

### TextDocumentObject.BeginEditCollection()

开始编�?
### TextDocumentObject.DefaultTabStop

制表符宽�?
### TextDocumentObject.EndEditCollection()

结束编辑

### TextDocumentObject.Name

文件�?
### TextDocumentObject.New()

新建文件

### TextDocumentObject.Open(filename,flags,codepage)

打开文档

### TextDocumentObject.Range(first,lim)

返回选区

### TextDocumentObject.RangeFromPoint(x,y)

指定坐标返回选区

### TextDocumentObject.Redo(number)

重做

### TextDocumentObject.Save(filename,flags,codepage)

保存文档

### TextDocumentObject.Saved

是否保存

### TextDocumentObject.Selection

选区对象

### TextDocumentObject.Selection.Font

字体

[返回对象:TomTextFontObject](#TomTextFontObject)

### TextDocumentObject.Undo(number)

撤消

### TextDocumentObject.tomFalse

假�?
### TextDocumentObject.tomToggle

切换原来的�?
### TextDocumentObject.tomTrue

真�?
### TextDocumentObject.tomUndefined

未定义�?
## TomTextFontObject 成员列表

### TomTextFontObject.Bold

是否粗体,

可使用tomTrue,tomFalse等�?
### TomTextFontObject.ForeColor

字体颜色

### TomTextFontObject.Name

字体�?
### TomTextFontObject.Size

字体大小

## charformat2Object 成员列表

### charformat2Object.backColor

背景颜色，GDI 颜色格式�?0xBBGGRR ）�?
### charformat2Object.bold

是否粗体，仅用于写入样式�?
设置了这个值会在应用样式前自动修改 weight 属性�?
### charformat2Object.charSet

字符�?
### charformat2Object.disabled

偏移一个像素，仅用于写入样式�?
### charformat2Object.effects

效果

### charformat2Object.faceName

字体�?
### charformat2Object.getFont()

返回LOGFONT对象

返回 LOGFONT 对象

[返回对象:logfontObject](#logfontObject)

### charformat2Object.italic

是否斜体，仅用于写入样式�?
### charformat2Object.lcid

区域ID

### charformat2Object.mask

掩码，这个一般不用管

### charformat2Object.pitchAndFamily

字体�?
### charformat2Object.point

字体大小，以 pt 为单位。仅用于写入样式�?
在设置样式时指定 point 会在应用样式前自动修�?yHeight 的值�?
修改字体大小请在窗体显示并且 DPI 初始化缩放完成以后再设置，不然会被重复放大�?
### charformat2Object.protected

保护文本，修改时触发 onProtected 事件�?
仅用于整个控件，不适用于部分选区�?
此属性仅用于写入样式�?
### charformat2Object.spacing

字体间距

### charformat2Object.strikeout

是否显示删除线，仅用于写入样式�?
### charformat2Object.textColor

字体颜色，GDI 颜色格式�?0xBBGGRR ）�?
### charformat2Object.underline

是否粗体，仅用于写入样式�?
### charformat2Object.underlineType

下划线类�?
### charformat2Object.weight

字体重量

### charformat2Object.yHeight

字体大小，以 twips 为单位�?
修改字体大小请在窗体显示并且 DPI 初始化缩放完成以后再设置，不然会被重复放大�?
### charformat2Object.yOffset

偏移

### 自动完成常量

\_CFE\_ALLCAPS=0x80

\_CFE\_AUTOBACKCOLOR=0x4000000

\_CFE\_AUTOCOLOR=0x40000000

\_CFE\_BOLD=1

\_CFE\_DISABLED=0x2000

\_CFE\_EMBOSS=0x800

\_CFE\_HIDDEN=0x100

\_CFE\_IMPRINT=0x1000

\_CFE\_ITALIC=2

\_CFE\_LINK=0x20

\_CFE\_OUTLINE=0x200

\_CFE\_PROTECTED=0x10

\_CFE\_REVISED=0x4000

\_CFE\_SHADOW=0x400

\_CFE\_SMALLCAPS=0x40

\_CFE\_STRIKEOUT=8

\_CFE\_SUBSCRIPT=0x10000

\_CFE\_SUPERSCRIPT=0x20000

\_CFE\_UNDERLINE=4

\_CFM\_ALL=-134217665

\_CFM\_ALL2=-16777217

\_CFM\_ALLCAPS=0x80

\_CFM\_ANIMATION=0x40000

\_CFM\_BACKCOLOR=0x4000000

\_CFM\_BOLD=1

\_CFM\_CHARSET=0x8000000

\_CFM\_COLOR=0x40000000

\_CFM\_DISABLED=0x2000

\_CFM\_EFFECTS=0x4000003F

\_CFM\_EFFECTS2=0x44037FFF

\_CFM\_EMBOSS=0x800

\_CFM\_FACE=0x20000000

\_CFM\_HIDDEN=0x100

\_CFM\_IMPRINT=0x1000

\_CFM\_ITALIC=2

\_CFM\_KERNING=0x100000

\_CFM\_LCID=0x2000000

\_CFM\_LINK=0x20

\_CFM\_OFFSET=0x10000000

\_CFM\_OUTLINE=0x200

\_CFM\_PROTECTED=0x10

\_CFM\_REVAUTHOR=0x8000

\_CFM\_REVISED=0x4000

\_CFM\_SHADOW=0x400

\_CFM\_SIZE=0x80000000

\_CFM\_SMALLCAPS=0x40

\_CFM\_SPACING=0x200000

\_CFM\_STRIKEOUT=8

\_CFM\_STYLE=0x80000

\_CFM\_SUBSCRIPT=0x30000

\_CFM\_SUPERSCRIPT=0x30000

\_CFM\_UNDERLINE=4

\_CFM\_UNDERLINETYPE=0x800000

\_CFM\_WEIGHT=0x400000

\_CFU\_CF1UNDERLINE=0xFF

\_CFU\_INVERT=0xFE

\_CFU\_UNDERLINE=1

\_CFU\_UNDERLINEDASH=5

\_CFU\_UNDERLINEDASHDOT=6

\_CFU\_UNDERLINEDASHDOTDOT=7

\_CFU\_UNDERLINEDOTTED=4

\_CFU\_UNDERLINEDOUBLE=3

\_CFU\_UNDERLINEDOUBLEWAVE=0xB

\_CFU\_UNDERLINEHAIRLINE=0xA

\_CFU\_UNDERLINEHEAVYWAVE=0xC

\_CFU\_UNDERLINELONGDASH=0xD

\_CFU\_UNDERLINENONE=0

\_CFU\_UNDERLINETHICK=9

\_CFU\_UNDERLINETHICKDASH=0xE

\_CFU\_UNDERLINETHICKDASHDOT=0xF

\_CFU\_UNDERLINETHICKDASHDOTDOT=0x10

\_CFU\_UNDERLINETHICKDOTTED=0x11

\_CFU\_UNDERLINETHICKLONGDASH=0x12

\_CFU\_UNDERLINEWAVE=8

\_CFU\_UNDERLINEWORD=2

\_ENM\_CHANGE=0x1

\_ENM\_CORRECTTEXT=0x400000

\_ENM\_DRAGDROPDONE=0x10

\_ENM\_DROPFILES=0x100000

\_ENM\_IMECHANGE=0x800000

\_ENM\_KEYEVENTS=0x10000

\_ENM\_LANGCHANGE=0x1000000

\_ENM\_LINK=0x4000000

\_ENM\_LOWFIRTF=0x8000000

\_ENM\_MOUSEEVENTS=0x20000

\_ENM\_NONE=0x0

\_ENM\_OBJECTPOSITIONS=0x2000000

\_ENM\_PAGECHANGE=0x40

\_ENM\_PARAGRAPHEXPANDED=0x20

\_ENM\_PROTECTED=0x200000

\_ENM\_REQUESTRESIZE=0x40000

\_ENM\_SCROLL=0x4

\_ENM\_SCROLLEVENTS=0x8

\_ENM\_SELCHANGE=0x80000

\_ENM\_UPDATE=0x2

\_IMF\_AUTOFONT=2

\_IMF\_AUTOFONTSIZEADJUST=0x10

\_IMF\_AUTOKEYBOARD=1

\_IMF\_CLOSESTATUSWINDOW=8

\_IMF\_DUALFONT=0x80

\_IMF\_FORCEACTIVE=0x40

\_IMF\_FORCEDISABLE=4

\_IMF\_FORCEENABLE=2

\_IMF\_FORCEINACTIVE=0x80

\_IMF\_FORCENONE=1

\_IMF\_FORCEREMEMBER=0x100

\_IMF\_IMEALWAYSSENDNOTIFY=8

\_IMF\_IMECANCELCOMPLETE=4

\_IMF\_MULTIPLEEDIT=0x400

\_IMF\_SMODE\_NONE=2

\_IMF\_SMODE\_PLAURALCLAUSE=1

\_IMF\_UIFONTS=0x20

\_IMF\_VERTICAL=0x20

\_SCF\_ALL=4

\_SCF\_ASSOCIATEFONT=0x10

\_SCF\_ASSOCIATEFONT2=0x40

\_SCF\_DEFAULT=0

\_SCF\_NOKBUPDATE=0x20

\_SCF\_SELECTION=1

\_SCF\_USEUIRULES=8

\_SCF\_WORD=2

\_SFF\_PWI=0x800

\_SF\_PWI=0x10802

\_SF\_RTF=2

\_SF\_TEXT=1

\_SF\_UNICODE=0x10

\_SF\_UTEXT=0x11

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/win/ui/ctrl/richedit.md)

