[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# win.subclass 库模块帮助文�?
## win 成员列表

### win.subclass

窗口子类�?

即替换当前进程内指定窗口的消息回调函�?

用于个别无法直接指定消息回调函数的窗�?
### win.subclass()

[返回对象:winsubclassObject](#winsubclassObject)

### win.subclass(窗口对象, 消息回调函数)

```aardio aardio
win.subclass(
    hwnd/*窗口对象或句�?/,function (hwnd,message,wParam,lParam) {

    })

```

## winsubclassObject 成员列表

### winsubclassObject.free()

取消子类�?

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/win/subclass.md)

