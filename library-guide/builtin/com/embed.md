[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# com�?嵌入控件

使用 com.CreateEmbed 函数在窗体上嵌入可视化控件�?
参�? [事件触发接口](event.html)

## com.CreateEmbed [\#](\#createEmbed)

### 1\. 函数原型�?
`容器对象 = com.CreateEmbed( 容器对象,窗口或控件对�?progId)`

`容器对象 = com.CreateEmbed( 容器对象,窗口或控件对�?comObject)`

`容器对象 = 窗口或控件对�?createEmbed(progId,容器对象)`

`容器对象 = 窗口或控件对�?createEmbed(comObject,容器对象)`

### 2\. 函数说明�?
所有窗体或控件都象都提供了 createEmbed 函数。一般不会调�?com.CreateEmbed 而是调用窗体或控件的 createEmbed 函数。窗体或控件�?createEmbed 函数提供了更完善的功能�?
此函数的作用是创�?COM 控件并将 COM 控件嵌入到指定的窗口或控件对象�?
- 容器对象是可选参数，如果不指定则默认会创建一个容器对象。如果指定容器对象，则容器对象必须是一�?table 对象�?- 窗口或控件对象指 win.form 对象�?winform 窗体上的控件对象, 指定的窗口或控件对象作会作为 COM 控件的宿主窗口，也是 COM 控件窗口的父窗口�?- [progId 参数](base.html#id) 指定要创建的嵌入�?COM 对象类名, 也可以直接指定一个创建好�?COM 对象替代 progId 参数�?
容器对象的作用是接管 COM 对象�?
容器对象可通过添加成员函数响应 COM对象 事件�?
容器对象的另一个主要作用是充当访问 COM 对象的中间代理对象。通常使用 util.metaProperty 为容器对象添加属性元表，属性元表可拦截属性、函数调用并调用实际�?COM 控件�?
容器对象包含以下成员�?
1. 容器对象.\_object

   指向真正�?COM 控件对象�?
   �?aardio �?下划线开始的成员是只读的不可修改，同时也是在提醒你这是隐藏的对象。如果不是清楚的了解这些对象的作用，不应当去使用这些成员对象。在开发环境中,智能提示默认不会提示下划线开始的成员,而是试图隐藏它们，只有你输入下划线以后，这些隐藏的成员才会出现在自动提示列表中�?
2. 容器对象.\_form

   指向 COM 控件的容器窗口�?
3. 容器对象.\_host

   COM 控件 OLE 宿主对象。提供部�?OLE 接口函数，一般没必要直接使用这个对象�?
   _host.close() = 关闭对象_
   _\_host.\_adjust() = 自动调整控件窗口大小_
   _\_host.tranacc(MSG消息对象) = 解析快捷�?如果是快捷键返回真值_
   _\_host.doObjectVerb( \_OLEIVERB_\_ ) = 执行指定的动词命�?

我们可以直接使用 `var comObject = 容器对象._object` 获得 COM 控件对象，然后直接操�?comObject �?
但是通常我们需要容器对象，这是因为�?
- 我们通常需要对 COM 控件做进一步的封装以增强或简�?COM 控件的功能�?COM 控件自己已经有了锁定的元表不能被替换，所以最好的方式是用一个容器对象去封装 COM 对象。参考： [元表 \- 代理表](../../../language-reference/datatype/table/meta.html#proxy)
- 窗口对象提供�?CreateEmbed 函数会自动将容器对注册为 COM 控件的事件表，可以直接在容器对象上添�?COM 事件回调函数�?
如果我们需要上面的好处，又不希望为 COM 对象写一个库做一些封装的操作，可以改用下面的 com.createEmbedEx 函数。com.createEmbedEx 会将容器对象创建为默认的代理表并可以直接访问 COM 对象�?
## com.createEmbedEx [\#](\#createEmbedEx)

### 1\. 函数原型�?
`容器对象 = com.createEmbedEx( 容器对象,窗口或控件对�?progId)`

`容器对象 = com.createEmbedEx( 容器对象,窗口或控件对�?comObject)`

`容器对象 = 窗口或控件对�?createEmbedEx(progId,容器对象)`

`容器对象 = 窗口或控件对�?createEmbedEx(comObject,容器对象)`

### 2\. 函数说明�?
所有参数的用法与返回的容器对象�?[com.createEmbed](#createEmbed) 相同�?
所有窗体或控件都象都提供了 createEmbedEx 函数。一般不会调�?com.createEmbedEx 而是调用窗体或控件的 createEmbedEx 函数。窗体或控件�?createEmbedEx 函数提供了更完善的功能�?
此函数的主要作用�?createEmbed 一样用于创�?COM 控件并将 COM 控件嵌入到指定的窗口或控件对象。但�?createEmbed 返回的宿主对象需要我们自己添加元表或属性元表去封装�?COM 控件的操作�?
createEmbedEx 函数返回的容器对象已自动添加元表并成为了 COM 对象�?[代理表](../../../language-reference/datatype/table/meta.html#proxy)，可通过容器对象的成员代理访�?COM 对象成员。也可以通过指定容器对象的成员函数响�?COM 对象事件�?
容器对象�?**event** 成员�?COM 对象默认的事件监听器。如果在容器对象上添加成员回调函数则会默认写入到 **event** 事件表�?
## 嵌入控件示例

下面是一个嵌�?COM 控件的完整示例：

```aardio aardio
import win.ui;
/*DSG{{*/
var winform = win.form(text="嵌入 COM 控件";right=759;bottom=469)
winform.add(
lbStatus={cls="static";left=25;top=435;right=725;bottom=460;db=1;dl=1;dr=1;transparent=1;z=2};
static={cls="static";text="Static";left=11;top=8;right=744;bottom=426;db=1;dl=1;dr=1;dt=1;transparent=1;z=1}
)
/*}}*/

//嵌入 COM 控件，宿主窗口这里指定为 winform.static
var embedObject= winform.static.createEmbedEx("Shell.Explorer.2");

//这下定义事件回调函数就省事了( 因为 embedObject 是默认的 COM 事件监听�?
embedObject.StatusTextChange = function(text) {
    winform.lbStatus.text = text;
}

//通过控件容器调用 COM 对象打开指定的网�?embedObject.Navigate("about:test");

winform.show();
win.loopMessage();

```

### 容器对象接管�?COM 对象的访问与操作

在上面的示例中，当我们调用：

```aardio aardio
embedObject.Navigate("about:test");

```

实际上会自动转换为调用：

```aardio aardio
embedObject._object.Navigate("about:test")

```

embedObject 已封装为�?COM 控件代理对象，访�?embedObject 的成员会自动转为调用 embedObject.\_object （真正的 COM 控件对象）�?
### createEmbedEx 具体执行了什么操�?
代码 `var embedObject= winform.static.createEmbedEx("Shell.Explorer.2")` 执行了以下操作：

1. 创建容器对象 embedObject, 控件容器通常用于封装 COM 对象，同时也会注册为 COM 对象默认�?COM 事件监听器�?2. 创建 COM 对象（Shell.Explorer 对象�?并存�?embedObject.\_object，注意这才是真正�?COM 对象�?3. 创建 COM 控件宿主对象并存�?embedObject.\_host，这个对象会提供部分 OLE 接口函数，一般没必要直接使用这个对象�?4. �?COM 对象嵌入宿主窗口并显示，宿主窗口存为 embedObject.\_form�?5. 在宿主窗口调整大小时自动调整 COM 控件窗口大小�?6. 优化 COM 控件绘图效果�?   \> 宿主窗口一般不需要绘图，所以对宿主窗口默认会执行以下操作：
   如果宿主窗口�?win.form 对象，且未指�?onEraseBkgnd 事件，那么会自动添加 embedObject.\_form.onEraseBkgnd = lambda() 0;
   如果宿主窗口是其他控件，自动添加 \_WS\_CLIPCHILDREN 样式，并移除 \_WS\_EX\_TRANSPARENT 扩展样式�?7. 创建 embedObject.\_\_event\_\_ 并注册为默认事件表�?8. 在宿主窗口销毁前自动解除默认事件监听器并释放 COM 对象。注意在 aardio 里下划线开头的成员是只读的，并且在智能提示候选列表里是默认隐藏的(�?\_ 就会出来)�?9. �?embedObject 转换�?embedObject.\_object �?embedObject.\_\_event\_\_ 的代理表，接管对 COM 控件以及事件表的访问�?
容器对象 embedObject 通常用于实现 COM 代理对象，用于拦截、封装对 embedObject.\_object 的操作�?winform.static.createEmbedEx() 函数会将容器对象创建�?COM 对象�?COM 事件表的代理对象，接管对 COM 控件以及事件表的访问�?
如果希望自定义代理层更精细地封装 COM 接口，请改用 winform.static.createEmbed() 函数创建控件（函数名字后面少�?Ex ）。winform.static.createEmbed() 函数不会创建默认代理�?
可在标准�?win.ui.ctrl.metaProperty 内可以查看这 createEmbed，createEmbedEx 函数的源码�?
### COM 控件对象本身默认不能直接添加事件

要注�?COM 控件对象本身并不能直接添加事件，例如下面的代码是错误的：

`embedObject._object.StatusTextChange = function(text) {}`

无论�?winform.static.createEmbedEx() 还是 winform.static.createEmbed() 返回的对象都可以通过容器对象添加事件，正确写法是�?
`embedObject.StatusTextChange = function(text) {}`

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-guide/builtin/com/embed.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-guide/builtin/com/embed.md')

