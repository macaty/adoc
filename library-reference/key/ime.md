[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# key.ime 库模块帮助文�?
## key.ime 成员列表

输入法相关操�?
### key.ime.activate(键盘布局句柄,选项)

激活指定的键盘布局

参数二可省略,使用 _KLF_ 前缀常量指定选项

### key.ime.capital()

是否大写状�?
### key.ime.changeRequest(0)

切换为上一个键盘布局

### key.ime.changeRequest(0x4090409)

切换为英文键盘布局

### key.ime.changeRequest(0x8040804)

切换为中文键盘布局

### key.ime.changeRequest(1)

切换为下一个键盘布局

### key.ime.changeRequest(hkl,hwnd,wParam)

发送\_WM\_INPUTLANGCHANGEREQUEST消息通知窗口改变输入�?

hkl可用数值或指针指定键盘布局,

@hwnd参数指定要检测的窗口句柄，省略则默认设为前景窗口

其他参数可省�?
### key.ime.control(hwnd,command,data)

发送\_WM\_IME\_CONTROL消息到指定窗�?
@hwnd参数指定目标窗口句柄，省略则默认设为前景窗口,

其他参数请参考微软文�?
### key.ime.each()

```aardio aardio
for(hKey,lang,name,description in key.ime.each() ){
    /*hKey:键盘布局句柄 lang:语言ID name:输入法名 description:描述*/
}

```

### key.ime.getConversionMode(hwnd)

返回输入法打开状�?

返回值为数值，可用 _IME\_CMODE_ 前缀的常量按位取值�?
@hwnd参数指定要检测的窗口句柄，省略则默认设为前景窗口

### key.ime.getCurrent(线程ID)

返回当前键盘布局句柄�?
参数可选，默认参数为当前线程ID�?
注意现在这个返回值里实际上只有语言 ID 有意义，

请参�?key.ime.getCurrentLangId 函数源代�?
注意如果目标线程不响应输入消息，例如一�?sleep 可能返回旧的键盘布局

cmd.exe 窗口可能会返�?null

### key.ime.getCurrentLangId(线程ID)

返回指定线程键盘布局语言ID

如果不指定参数则默认取当前线程ID

注意如果目标线程不响应输入消息，例如一�?sleep 可能返回旧的键盘语言ID�?
cmd.exe 窗口可能会返�?0

### key.ime.getCurrentLangIdByHwnd(hwnd)

返回当指定窗口键盘布局语言ID

如果不指定参数则默认取前台窗口句�?
注意如果目标线程不响应输入消息，例如一�?sleep 可能返回旧的键盘语言�?
cmd.exe 窗口可能会返�?0

### key.ime.getDescription(键盘布局句柄)

返回键盘布局描述

对默认中英文键盘无效

### key.ime.getLangId(键盘布局句柄)

返回语言代码

### key.ime.getList()

返回键盘布局句柄数组

WIN10上只会返回键盘语言，不会列出输入法

### key.ime.getName(键盘布局句柄)

返回键盘布局名称

### key.ime.getOpenStatus(hwnd)

当前输入法是否打开中文输入

@hwnd参数指定要检测的窗口句柄，省略则默认设为前景窗口,

注意有些输入法打开但切换到英文模式也会返回 false,

而微软输入法打开状态不论中英都会返�?true,

所以用这个很难判断当前真正的输入模�?
### key.ime.loadActivate("输入法名")

参数也可以是键盘布局句柄

加载并激活指定键盘布局

### key.ime.loadByName("键盘布局�?,选项)

载入指定的键盘布局

对默认中英文键盘无效

参数二可省略,使用 _KLF_ 前缀常量指定选项

### key.ime.setConversionMode(convMode,hwnd)

设置输入法打开状态，

参数�?_IME\_CMODE_ 前缀的常量按位或运算的数值�?
@hwnd参数指定目标窗口句柄，省略则默认设为前景窗口

### key.ime.setOpenStatus(status,hwnd)

status设为0关闭中文输入

@hwnd参数指定目标窗口句柄，省略则默认设为前景窗口

### key.ime.state

返回输入法状态，

请参�?

[输入法状态检测规则与原理](../../library-guide/std/key/imeState.html)

[key.ime.stateBar](ime.stateBar.html)

### key.ime.state(hwnd)

返回输入法状态，

@hwnd 参数指定要检测的窗口句柄，省略则默认设为前景窗口�?
建议使用 winex.caret 取到光标所有窗口句柄作为参数，参�?key.ime.stateBar�?
首个返回值为是否启用输入转换（例如输入中、日、韩等文字），false 为英文输入状态，

第二个返回值用一个数值表示标点模式：

1 英文半角标点

2 英文全角标点

3 中文标点

0 已关闭输入转�?
null 已关闭输入转�?
第三个返回值为键盘语言 ID�?
第四个返回值为原始 Conversion Mode

### 自动完成常量

\_IME\_CMODE\_ALPHANUMERIC=0

\_IME\_CMODE\_CHARCODE=0x20

\_IME\_CMODE\_EUDC=0x200

\_IME\_CMODE\_FIXED=0x800

\_IME\_CMODE\_FULLSHAPE=8

\_IME\_CMODE\_HANJACONVERT=0x40

\_IME\_CMODE\_KATAKANA=2

\_IME\_CMODE\_LANGUAGE=3

\_IME\_CMODE\_NATIVE=1

\_IME\_CMODE\_NOCONVERSION=0x100

\_IME\_CMODE\_RESERVED=0xF0000000

\_IME\_CMODE\_ROMAN=0x10

\_IME\_CMODE\_SOFTKBD=0x80

\_IME\_CMODE\_SYMBOL=0x400

\_IME\_SYMBOLMODE\_FULLSHAPE=2

\_IME\_SYMBOLMODE\_HALFSHAPE=1

\_IME\_SYMBOLMODE\_SYMBOL=3

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/key/ime.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/key/ime.md')

