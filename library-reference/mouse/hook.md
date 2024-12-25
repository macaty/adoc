[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# mouse.hook 库模块帮助文�?
重要说明

低级鼠标钩子只能用于界面线程，并且依赖界面线程创建的消息循环�?
低级鼠标钩子所在界面线程的任何耗时操作执行时间不应超过 200 毫秒�?耗时操作可能导致遗漏部分鼠标消息，如果耗时操作阻塞鼠标钩子消息超过一秒或超过注册表限制的更小时间�?系统可能会直接删除鼠标钩子（导致超级热键不可用）�?
建议将阻塞消息循环的耗时操作放到后台工作线程内执行，
请参考： [创建多线程](https://www.aardio.com/zh-cn/guide/language/thread.html)�?
## mouse 成员列表

### mouse.hook

低级鼠标钩子�?
低级鼠标钩子只能用于包含窗口消息循环的界面线程�?
鼠标钩子所在的界面线程如果有阻塞钩子消息的耗时操作，可能导致遗漏鼠标消息�?
耗时操作阻塞鼠标钩子消息超过一秒或注册表限制的更小时间，系统可能导致钩子失效�?
建议将阻塞消息循环的耗时操作应当放到后台工作线程内执行�?
### mouse.hook()

创建低级鼠标钩子

[返回对象:MouseHookObject](#MouseHookObject)

## MouseHookObject 成员列表

### MouseHookObject.close()

释放按键录制钩子

### MouseHookObject.proc

```aardio aardio
MouseHookObject.proc = function(msg,x,y,mouseData,injected,flags,timeStamp,extraInfo){
    if( injected ) return;//忽略模拟按键

    select(msg) {
        case 0x201/*_WM_LBUTTONDOWN*/{
            io.print("左键按下",x,y)
        }
        case 0x202/*_WM_LBUTTONUP*/{
            io.print("左键弹起",x,y)
        }
    }

    /*取消调用 return true;
注意钩子回调函数不要做耗时操作
耗时操作应改用线程或 winform.setTimeout 异步执行*/
}

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/mouse/hook.md)

