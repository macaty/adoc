[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# 窗口消息

窗口消息，就是指 Windows 发出的一个通知，告诉应用程序某个事情发生了。例如，单击鼠标、改变窗口尺寸、按下键盘上的一个键都会�?Windows 发送一个消息给应用程序。消息本身是作为一个记录传递给应用程序的，这个记录中包含了消息的类型以及其他信息。例如，对于单击鼠标所产生的消息来说，这个记录中包含了单击鼠标时的坐标�?
## 一、窗口消息范�?[\#](\#range)

**消息范围**

**表示**

0 ~ WM\_USER�?

操作系统保留的消息�?
**WM\_USER** ~ 0x7FFF

私有窗口级别的自定义消息�?
**WM\_APP** ~ 0xBFFF

应用程序级别的自定义消息。其�?xAAAA/\*\_WM\_AARDIO\_RESERVED\*/ �?0xBFFF �?aardio 标准库保留值请勿使用�?
0xC000 ~ 0xFFFF

::RegisterWindowMessage函数定义一个新的窗口消息，该消息保证在整个系统范围内是唯一的�?
0xFFFF ~

操作系统保留的消息�?
## 二、窗口消息循�?[\#](\#loopMessage)

对于每一个正在执行的 Windows 应用程序，操作系统为其建立一�?消息队列"，即应用程序消息队列，用来存放该程序可能创建的各种窗口的消息。在 aardio 窗口程序中，调用 win.loopMessage 启动窗口消息循环，用来从程序的消息队列中检索窗口消息并把它们分发到相应的窗口函数中�?并且触发 aardio 中的 消息回调函数 wndproc、命令回调函�?oncommand、通知回调函数 onnotify 等等�?
"消息循环"实际也就是窗口程序的主循环，win.loopMessage 退出则窗口程序终止�?
应用程序可以通过调用 `win.quitMessage()` 退出消息循环。在 aardio 中当界面线程的所有非模态、非 MessageOnly 的独立窗口（ �?mainForm 窗口 ）都关闭后，将会自动调用 `win.quitMessage()` 并终止消息循环（之后如果没有执行其他代码就会退出界面线程）。如果显式指�?`win.autoQuitMessage` 的值为 `false` 则禁止当前线程在关闭前述窗口时自动调�?`win.quitMessage()` 。如果窗口对象自身的 `autoQuitMessage` 的属性值为 `false` 也会禁止在关闭该窗口时自动调�?`win.quitMessage()` �?
请参考： [启动与退出窗口消息循环](../_.html#loopMessage)

## 三、响应控件命令、通知消息 [\#](\#oncommand-onnotify)

对于一般的窗口控件发生的事件，通过创建响应命令、通知消息的函数就可以处理了�?一个窗口内的控件发生了一些事情，需要通知父窗口，就会发�?\_WM\_COMMAND 或�?\_WM\_NOTIFY 消息给父窗口.

最�?Windows 3.x 就有的标准控�?Standard Controls)，如 Edit，Combobox，Listbox，Button 等，发送的控件通知消息的格式是 WM\_COMMAND；而后期的 Win32 通用控件(Common Controls)，如 List View，Image List，IP Address，Tree View，Toolbar 等，发送的都是 WM\_NOTIFY 控件通知消息。另外，当用户选择菜单的一个命令项，也会发�?\_WM\_COMMAND 消息�?
早期开发桌面软件使用的�?C++ 这样的静态语言，通常主要代码都是写在父窗口中，所以这种通知父窗口的消息一定意义上来说提供了方便。但是在 aardio 这样的动态语言中这种方式意义不大，在父窗口上处理所有子控件的消息其实是想对麻烦显不必要的，所�?aardio 将这些消息重新发回给控件对象自己处理�?
�?aardio 中通过控件�?oncommand 函数处理自身发出�?\_WM\_COMMAND 消息，通过控件�?onnotify 函数处理自身发出�?\_WM\_NOTIFY 消息�?
�?aardio 开发环境的窗体设计器中，右键点击控件，

在弹出菜单中点击「响应命令」就可以为该控件添加 oncommand 函数�?
在弹出菜单中点击「响应通知」就可以为该控件添加 onnotify 函数�?
在�?aardio 开发环�?/ 窗体设计器」放置的「窗口控件」上直接「双击鼠标左键」可以快速创建或跳转�?oncommand �?onnotify 函数，一般标准控件双击会创建 oncommand 函数( 如果已创�?oncommand 则跳转到该函�?)，通用控件双击会创�?onnotify 函数( 如果已创�?onnotify 则跳转到该函�?)�?
## 四、窗口消息回�?[\#](\#wndproc)

如果你需要进一步拦截所有消息，�?aardio 里，非常的简单�?我们只要右键点击窗口或控件，在弹出的右键菜单里点击【创建窗口消息回调函数】就可以自动创建如下的消息回调函数：

```aardio aardio
winform.wndproc = function(hwnd,message,wParam,lParam){
    select( message ) {
        case 0x205/*_WM_RBUTTONUP*/{
            //鼠标右键弹起,下面获取坐标
            var x,y = win.getMessagePos(lParam);

        }
        else{

        }
    }
    //无返回值则继续调用默认回调函数
}

```

在消息回调函数里，可以处理控件或窗口的所有消息�?
wndproc 回调参数说明�?
- hwnd 当前窗口自己的窗口句柄，�?aardio 里一般我们不用管这个参数�?- wParam 通常是一个与消息有关的常量值，也可能是窗口或控件的句柄�?
- lParam 这是一个数值。但是根据不同的消息，它们有不同的意义，例如在鼠标右键弹起消息里�?:LOWORD(lParam) �?lParam 的低位表示x坐标, ::HIWORD(lParam) 取出 lParam 的高位表示y坐标，而在有些消息里可能要转换为指针处理�?- message 用于区别其他消息的常量值，这些常量值通常�?`_WM_` 前缀开始，�?aardio 里输入这个常量前缀，编辑器会显示常量列表与常量值�?
## 五、发送消�?[\#](\#send)

使用 `import win;` 语句会自动以下的消息 API 函数�?
```aardio aardio
::RegisterWindowMessage = ::User32.api("RegisterWindowMessageW","INT(ustring)");
::PostMessage = ::User32.api("PostMessageW","addr(addr hwnd,INT msg,ADDR wParam,addr lParam)")
::PostThreadMessage = ::User32.api("PostThreadMessageW","addr(int idThread,INT msg,ADDR wParam,addr lParam)");
::SendMessage = ::User32.api("SendMessageW","addr(addr hwnd,INT msg,ptr wParam,ptr lParam)")
::SendMessageInt = ::User32.api("SendMessageW","addr(addr hwnd,INT msg,ADDR wParam,addr lParam)")
::SendMessageByInt = ::User32.api("SendMessageW","addr(addr hwnd,INT msg,int &wParam,int &lParam)")
::SendMessageByString = ::User32.api("SendMessageW","addr(int,INT,int,string &lParam)")
::SendMessageByStr = ::User32.api("SendMessageW","addr(int,INT,int,ustring &lParam)")
::SendMessageByStruct = ::User32.api("SendMessageW","addr(int,INT,int,struct &lParam)")
::SendMessageTimeout = ::User32.api("SendMessageTimeoutW","addr(addr hwnd,INT msg,ptr wParam,ptr lParam,INT flags,INT timeout,int & resultult)")

```

注意�?aardio 中并不是一定要先声�?API 才能调用，也可以直接调用 `::User32.SendMessage()` �?`::User32.PostMessage()` 函数�?直接调用 `::User32.SendMessage()` �?`::User32.PostMessage()` 的好处是参数可以使用任何可以兼容转换为该API 参数类型的数据类型，参数可以使用的数据类型更多�?
而声明的 API 函数有更严格的参数类型检查，也必须严格使用与声明的参数类型兼容的参数，不同的参数类型可能要声明不同的 API 函数�?
PostMessage 系列函数只负责将消息放到消息队列中然后直接返�?消息�?win.loopMessage() 处理.

工作线程如果�?UI 线程消息队列快速发送大量的消息,导至消息队列大小超过系统限制,会导致后续消息丢�?无法正常响应用户操作.

SendMessage 系列函数调用窗口回调函数,并等待直到获取返回代�?消息不会放入队列�?即不会被 win.loopMessage() 处理 在多线程中，如果多个线程都频繁的调用SendMessage系列函数,因为该函数会在相同的GUI线程中阻塞处�? 这会导致多线程实际上失去并发执行的效�?

了解消息可以做很多有趣的事，
例如我们可以不要标题栏（在窗体属性中将text属性清空），不要边框�?自已用控件来模拟 Windows 的标题栏以及边框，用图片控件做出漂亮的无边框窗体�?在控件的消息回调中拦�?\_WM\_LBUTTONDOWN �?
示例�?
```aardio aardio
// 模拟标题栏，这是 winform.hitCaption() 函数的主要代�?::User32.PostMessage(hwnd,0xA1/*_WM_NCLBUTTONDOWN*/,0x2/*_HTCAPTION*/,0)

// 模拟上下左右8个方向调整窗体大小的边框，这是库 win.ui.resizeBorder 的主要代�?::User32.SendMessage(hwnd,0xA1/*_WM_NCLBUTTONDOWN*/,0xC,0);
::User32.SendMessage(hwnd,0xA1/*_WM_NCLBUTTONDOWN*/,0xF,0);
::User32.SendMessage(hwnd,0xA1/*_WM_NCLBUTTONDOWN*/,0xA,0);
::User32.SendMessage(hwnd,0xA1/*_WM_NCLBUTTONDOWN*/,0xB,0);
::User32.SendMessage(hwnd,0xA1/*_WM_NCLBUTTONDOWN*/,0xD,0);
::User32.SendMessage(hwnd,0xA1/*_WM_NCLBUTTONDOWN*/,0x10,0);
::User32.SendMessage(hwnd,0xA1/*_WM_NCLBUTTONDOWN*/,0xE,0);
::User32.SendMessage(hwnd,0xA1/*_WM_NCLBUTTONDOWN*/,0x11,0);

// 模拟窗体最小化，这�?winform.hitMin() 函数的主要代�?::User32.PostMessage(hwnd,0x112/*_WM_SYSCOMMAND*/,0xF020/*_SC_MINIMIZE*/,0);

// 模拟窗体最大化，这�?winform.hitMax() 函数的主要代�?::User32.PostMessage(hwnd,0x112/*_WM_SYSCOMMAND*/,0xF030/*_SC_MAXIMIZE*/,0);

// 模拟窗体最大化后还原，这是 winform.hitClose() 函数的主要代�?::User32.PostMessage(hwnd,0x112/*_WM_SYSCOMMAND*/,0xF120/*_SC_RESTORE*/,0);

```

注意�?aardio 标准库中已经封装好了以上范例中类似的函数�?
�?winform 为一�?win.form 对象，则�?
```aardio aardio
//模拟点击窗口最大化按钮
winform.hitMax()

//模拟点击窗口最小化按钮
winform.hitMin()

//模拟点击窗口关闭按钮,也可以用 winform.close()
winform.hitClose()

//模拟点击窗口标题栏，通常在无边框窗口�?winform.onMouseDown 事件中调用�?winform.hitCaption()

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-guide/std/win/ui/msg.md)

