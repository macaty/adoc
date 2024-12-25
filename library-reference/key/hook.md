[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# key.hook 库模块帮助文�?
重要说明

低级键盘钩子只能用于界面线程，并且依赖界面线程创建的消息循环�?
低级键盘钩子所在界面线程的任何耗时操作执行时间不应超过 200 毫秒�?耗时操作可能导致遗漏部分键盘消息，如果耗时操作阻塞键盘钩子消息超过一秒或超过注册表限制的更小时间�?系统可能会直接删除键盘钩子（导致超级热键不可用）�?
建议将阻塞消息循环的耗时操作放到后台工作线程内执行，
请参考： [创建多线程](https://www.aardio.com/zh-cn/guide/language/thread.html)�?
勿滥用低级键盘钩子，
普通快捷键不必要使用此钩子，可参�?
aardio 范例 / Windows窗口应用 / 快捷键�?
## key 成员列表

### key.hook

低级键盘钩子�?
低级键盘钩子只能用于包含窗口消息循环的界面线程�?
键盘钩子所在的界面线程如果有阻塞钩子消息的耗时操作，可能导致遗漏键盘消息�?
耗时操作阻塞键盘钩子消息超过一秒或注册表限制的更小时间，系统可能导致钩子失效�?
建议将阻塞消息循环的耗时操作应当放到后台工作线程内执行�?
### key.hook()

创建低级键盘钩子

[返回对象:KeyHookObject](#KeyHookObject)

## KeyHookObject 成员列表

### KeyHookObject.close()

释放按键录制钩子

### KeyHookObject.mapKey

创建一个映射按键的 proc �?
用法请参考：范例/自动�?adb/安卓投屏

### KeyHookObject.mapKey(map,owner,hwnd)

参数 @map 可在 down 字段指定按键映射表，�?up 字段指定弹起键映射表�?
按键映射表的键应当为 key.VK 定义的键名，值为 @owner 的成员函数名�?
可选用 @hwnd 限定映射按键的窗口句�?
### KeyHookObject.proc

```aardio aardio
KeyHookObject.proc = function(msg,vkcode,scancode,injected,flags,timeStamp,extraInfo){
    if( injected ) return;//忽略模拟按键

    var kn = key.getName( vkcode );
    select(msg) {
        case 0x100/*_WM_KEYDOWN*/ ,0x104/*_WM_SYSKEYDOWN*/{
            io.print("按下",kn)
        }
        case 0x101/*_WM_KEYUP*/,0x105/*_WM_SYSKEYUP*/{
            io.print("弹起",kn)
        }
    }

    /*取消按键调用 return true;
注意钩子回调函数不要做耗时操作�?耗时超过一秒或超过注册表限制的更小时间�?系统会直接删除钩子，没有任何方法可以检查到删除操作�?可用 win.setTimeout 或创建线程执行耗时操作*/
}

```

### 自动完成常量

\_LLKHF\_ALTDOWN=0x20

\_LLKHF\_EXTENDED=1

\_LLKHF\_INJECTED=0x10

\_LLKHF\_UP=0x80

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/key/hook.md)

