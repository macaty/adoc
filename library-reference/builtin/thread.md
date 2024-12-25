[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# builtin.thread 库模块帮助文�?
## thread 成员列表

### thread.\_callableSerialize

界面线程内非窗口对象 \_serialize 元方法设定为此函�?可支持跨线程调用,

绑定此元方法后，对象传入其他线程后所有成员调用都将回到界面线程执�?
### thread.add(k,v)

对参数k指定线程共享变量名称的数值增加参数v指定的计�?
参数v可以使用负数执行减操�?
### thread.callWndMeta

跨线程传输的窗口对象元表,用于支持跨线程调�?
### thread.callable()

开启界面线程非窗口对象的多线程界面回调功能�?
此函数会将对象的\_serialize 元方法指定为 thread.\_callableSerialize,

用于在界面线程内启用对象跨线程调用支�?注意启用后无法撤�?

启用此特性后,对象传入其他线程后所有成员调用都将回到界面线程执�?

参数指定 talbe 类型对象

如果成功、或者对象已支持跨线程调用返�?true

失败返回null或false

### thread.createSuspended(suspended,cb)

suspended参数指定thread.create函数创建的线程是否为暂停状�?
如果@cb参数指定了线程函�?则执行线程函数后恢复原来的设�?
其他参数作为回调函数的参�?线程函数的返回值为此函数的返回�?
注意线程函数有独立的全局变量环境,线程引用的库应当在线程函数内 import

### thread.delay()

参数指定延时�?单位毫秒,参数不可省略,

导入 win 库的界面线程内会执行 win.delay�?
否则执行 sleep 函数�?
如果当前线程导入�?win 库则退出消息循环返回null,否则返回true

否则调用 sleep 函数并总是返回 true

### thread.init(k,v)

如果参数k指定名称的线程共享变量为空�?

则初始化该变量值为参数v指定的�?
### thread.invoke

创建线程但不返回线程句柄，线程句柄已自动关闭�?
### thread.invoke(aardio文件路径,调用参数)

创建线程运行 \*.aardio 文件，不返回线程句柄�?
该文件所在目录将被设定为此线程的应用程序根目�?

该目录下�?/lib/"目录将被设定为用户库目录,

在线程文件内可使用owner参数获取这里传入的首个调用参数�?
### thread.invoke(线程函数,其他调用参数)

```aardio aardio
thread.invoke(
    function(){
        /*创建线程但不返回线程句柄�?注意线程函数有独立的全局变量环境,线程引用的库应当在线程函数内 import*/
    }
)

```

### thread.invokeAndWait(func,...)

```aardio aardio
thread.invokeAndWait(func,...invokeAndWait(
    function(){
        import win;
        /*创建工作线程执行参数@1指定的线程函�?
参数@1之后的其他可选参数会作为调用线程函数的参数�?调用并等待线程函数执行完�?然后获取此线程函数的返回�?
在界面线程等待时界面仍可响应用户操作，线程函数的返回值会返回给调用线�?
线程函数拥有独立的全局变量，并应遵守多线程调用规则*/
    }
)

```

### thread.invokeEx(线程函数,其他参数)

```aardio aardio
thread.invokeEx(
    function(){
        /*创建线程并等待线程执行完�?然后自动关闭线程句柄�?可用于原生多线程回调函数中创建独立线程以启用 COM 接口,
注意线程函数有独立的全局变量环境,线程引用的库应当在线程函数内 import*/
    }
)

```

### thread.setAffinity(1,)

指定线程在哪个CPU上运�?成功返回原CPU序号,失败返回0,

参数@1指定CPU,参数@2指定线程句柄

省略参数@2在设置当前线�?
### thread.stillActive()

线程是否未退�?参数为线程句�?
### thread.var

创建线程共享变量 \- 可直接作为调用参数传入其他线�?
### thread.var()

[返回对象:threadvarObject](#threadvarObject)

### thread.var(name,value)

可选用参数@1指定共享变量名称,可选在参数@2中指定初始化�?

如果不指定共享变量名，则自动分配共享变量�?

线程共享变量不会自动释放,调用 set 函数设为 null 可删除线程变�?

如果确认没有线程再使用该变量，可调用 relase 函数释放共享变量�?

thread.var以及 thread.table 自动分配的线程共享变量名上限�?
:0x3FFFFFFFFFFFFC0000000000000 个�?
应及时调用返回对象的 release 函数释放不需要的线程共享变量

### thread.wait()

等待一个线程句柄返�?
可选使用第二个参数指定超时值（单位毫秒�?
成功返回true,超时返回false;

### thread.waitAll()

等待一个或多个线程返回

参数可以是多个线程句�?或包含多个线程句柄的数组

可选使用最后一个参数指定超时值（单位毫秒�?
成功返回值为�?失败返回�?

返回�?为错误类�?该值为字符�?timeout"表示超时

### thread.waitClose()

等待一个或多个线程返回,并释放所有线程句�?
参数可以是多个线程句�?或包含多个线程句柄的数组

### thread.waitOne

等待一个或多个线程其中一个返�?
如果在界面线程中调用这个函数，会在等待过程中响应用户输入消息�?
### thread.waitOne(...,timeout)

等待一个或多个线程其中一个返回，参数可以是多个线程句柄，

也可以用参数@1指定一个包含多个线程句柄的数组�?
注意线程句柄总数不能大于64个�?
可选使用最后一�?@timeout 参数指定超时值（单位毫秒�?
成功返回值为完成的句柄在数组中的索引,失败返回�?

返回�?为错误类�?该值为字符�?timeout"表示超时

## threadvarObject 成员列表

### threadvarObject.add()

增加数�?

共享变量之前必须是数值或者null�?

可以在参数中指定负数执行减操�?
### threadvarObject.get()

获取�?
### threadvarObject.release()

返回变量原来的�?

同时设为 null 并删除该变量�?
应及时释放不再使用的线程共享变量

### threadvarObject.set()

在参数@1中指定新的�?

不使用时一定要设置值为null以删除该变量

如果使用了共享变量名,

即使删除共享变量也不会再重复分配该变量名给新的线程变�?

除非调用release函数释放该变量名

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/builtin/thread.md)

