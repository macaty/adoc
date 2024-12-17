[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# console.int 库模块帮助文�?
## console 成员列表

### console.int

用于注册控制台中断信号触发器�?
导入此库会自动导�?console 库，并且退出线程时如果控制�?
仍在显示，则自动调用 console.pause 函数

### console.int()

[返回对象:consoleIntObject](#consoleIntObject)

### console.int(ctrlHandler,owner)

```aardio aardio
console.int(
    function(ctrlType){
        /*控制台退出前是否触发此线程函数�?可选用 @owner 指定线程函数�?owner 参数�?
使用前请先阅读多线程入门教程，了解线程函数基本规则�?
ctrlType �?null 表示控制台正常关闭，不可取消�?ctrlType �?0 表示按下 Ctrl+ C�?ctrlType �?1 表示按下 Ctrl + Break�?ctrlType �?0 �?1 时返�?true 可阻止控制台退出�?省略此函数时，则创建默认触发器并返回 true�?
在此函数内不应再使用任何控制台函�?/
    }
);

```

## consoleIntObject 成员列表

### consoleIntObject.isInterrupted()

控制台是否已收到中断信号�?
�?Ctrl + C ，Ctrl + Break 以后，无论是否阻止退出都会返�?true

### consoleIntObject.run(callback)

```aardio aardio
consoleIntObject.run(
    function(){
        /*如果控制台程序未退出，未按�?Ctrl + C�?则重复执行此回调函数，函数返�?false 退出循环�?
此函数可接收 run 函数除参�?@1 以外的余下参�?*/
    }
)

```

### consoleIntObject.setDelay()

参数 @1 指定控制台程序退出前的默认延迟，以毫秒为单位

如果直接关闭窗口�?
触发器可以拦截但无法阻止关闭�?
增加延迟可增加控制台程序退出前的等待时�?
延迟之前先设置中断状态，也不会阻止当前线程向下执�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/console/int.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/console/int.md')

