[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# builtin.com 库模块帮助文�?
## com 成员列表

COM 组件支持�?

虽然这是内置库，但例外的是这个库不会自动导入,

如果在已经导入win.ui 的界面线程，win.ui 会负责自动导�?com �?
[使用手册相关文档](../../library-guide/builtin/com/com.html)

### com.AddConnection

绑定事件监听对象

### com.AddConnection(COM对象,事件监听对象)

事件监听对象�?com.ImplInterface 创建

返回一个表示事件连接点�?cookie,

可用于释放绑定的 com.ReleaseConnection 函数�?
参数 @1 指定的对象如果被释放回收，事件监听也会自动解除�?
注意 excel.ActiveWorkbook 这种动态属性应当先保存到变量，再绑定事�?
### com.Connect

注册事件接收�?
此函数返回sink,cookie �?个返回值，

sink为事件接收器,cookie是一个数字�?用来记录连接点，

�?个返回值可以用�?com.ReleaseConnection 释放事件表�?
### com.Connect(COM对象,事件监听�?

参数 @2 指定一�?table 类型的表对象

该表对象被转换为COM对象的默认事件监听器并实现默认事件接�?

如果需要显式指定接口类型请使用 com.AddConnection�?
com.Connect 绑定的事件监听表会被强引用到 COM对象

如果COM对象与事件接收表存在循环引用自身会导致无法释�?

可用 com.ReleaseConnection 手动释放事件绑定,

或者改�?com.ConnectWeak,com.CreateEmbedEx 也可以避免该问题�?
参数 @1 指定的对象如果被释放回收，事件监听也会自动解除�?
注意 excel.ActiveWorkbook 这种动态属性应当先保存到变量，再绑定事�?
### com.ConnectWeak

注册弱引用自身的事件接收�?
此函数返回sink,cookie �?个返回值，

sink为事件接收器,cookie是一个数字�?用来记录连接点，

�?个返回值可以用�?com.ReleaseConnection 释放事件�?
### com.ConnectWeak(COM对象,事件接收�?

参数@2指定一个table类型的表对象

该表对象被创建为COM对象的默认事件接口并注册为事件接收器�?
在COM对象销毁前，com.Connect绑定的事件接收表会被强引用并被阻止回收，

如果COM对象与事件接收表存在循环引用自身会导致COM对象无法释放,

com.ConnectWeak函数通过创建一个中间代理对象弱引用事件接收表，可以避免该问题，

但要注意回调事件访问的owner对象是代理对�?使用owner.realSink可以获取真正的事件表

### com.CreateEmbed

创建 COM 控件对象,

通常不会直接使用此函�?

应改用窗口或控件对象提供�?CreateEmbed �?CreateEmbedEx 函数,

或�?com.lite 提供�?CreateEmbed �?CreateEmbedEx 函数

### com.CreateEmbed()

[返回对象:embedObject](../com/_.html#embedObject)

### com.CreateEmbed(embedObject,formOrCtrl,comObject)

创建 COM 控件对象并嵌�?@formOrCtrl 指定的窗体或控件窗口

@comObject 参数指定 com.IDispatch 对象,

@embedObject 用一个表指定容器对象

### com.CreateEmbed(embedObject,formOrCtrl,progId)

创建 COM 控件对象并嵌�?@formOrCtrl 指定的窗体或控件窗口

@progId 指定要创建的 COM 控件�?ProgID 或�?CLSID

@embedObject 用一个表指定容器对象

容器对象可以是一个空的表用于接管 COM对象

函数返回该容器对象并添加成员\_host,\_object,\_form

\_object 成员是创建的 COM对象 ,

\_form 是传入参数中�?@formOrCtrl,

\_host �?COM 控件宿主对象,提供部分 OLE 接口函数,

容器对象可通过添加成员函数响应 COM对象 事件�?
容器对象的另主要作用是充当访�?COM对象 的中间代理对象�?
通常使用 util.metaProperty 为容器对象添加属性元表，

属性元表可拦截属性、函数调用并调用 \_object 对象

### com.CreateEmbedEx

创建 COM 控件，返回控件容器对象�?
容器对象�?_object 成员是创建的 COM 对象。_

_容器对象�?\_\_event_\_ 成员�?COM 对象默认事件监听器�?
返回容器已添加元表，可通过容器对象的成员代理访�?COM 对象成员�?
也可以通过指定容器对象的成员函数响�?COM 对象事件

### com.CreateEmbedEx(clsId,ctrlOrForm,embedObject)

创建 COM 控件,返回控件容器对象�?
此函数返回的容器已添加元表并创建代理以直接访�?COM对象�?
也可以通过指定容器对象的成员函数响�?COM 对象事件�?
@clsId 指定控件 CLSID 或�?ProgID �?
可选用 @ctrlOrForm 指定宿主窗口�?
如果指定了窗主窗口，在窗口销毁时解除默认事件监听器并释放 COM 对象�?
可选在参数 @embedObjec 中指�?COM对象 绑定的容器对�?
### com.CreateObject("字符串参�?)

创建并返�?com.IDispatch 对象,参数@1可指�?CLSID �?ProgID,

创建失败会抛出异�?使用 com.TryCreateObject 代替不会抛异�?
### com.DoObjectVerb(OLE对象,-1)

执行OLE对象的动�?

参数2可使用\_OLEIVERB\_前缀常量

### com.DumpTypeInfo

输出 COM对象 类型信息、成员函数列表，

输出到控制台可使�?console.dump 函数�?
调用 com.tlbDoc.dump 函数可打�?COM对象 更详细的类型库信�?
### com.DumpTypeInfo(comObject)

返回一个字符串

包含 COM对象 类型信息、成员函数列�?

此函数不会输出到控制�?

输出到控制台请使�?console.dump 函数

### com.GetEnumerator()

获取枚举对象,

参数 @1 指定 COM对象

[返回对象:comEnumeratorObject](#comEnumeratorObject)

### com.GetIUnknown(COM对象 或指�?GUID)

使用 GUID 指定接口获取 com.IUnknown 托管指针

参数@1可是任何可以转换为指针的对象,与API参数规则相同,

可选在参数@2使用字符串或GUID指定接口

该指针自动管理引用计数，无须手动释放

### com.GetObject("字符串参�?)

从已运行的实例获取并返回 com.IDispatch 对象,

参数@1可指定CLSID或ProgID,也可指定打开的文件路�?�?doc 文件,

获取对象失败会抛出异�?使用 com.TryGetObject 代替不会抛异常�?
如果当前进程与目�?COM 服务进程不具有相同权限，则会报错『无效的操作』�?
### com.GetOrCreateObject("字符串参�?)

参数可指定一个或多个CLSID/ProgID,

首先调用 com.TryGetObject 尝试获取并返回已运行的实�?

如果失败则调�?com.TryCreateObject 函数尝试创建并返回对�?

创建失败返回null,错误信息,不会抛出异�?
如果当前进程与目�?COM 服务进程不具有相同权限，

�?TryGetObject 不能获取该进程创建的 COM 对象�?
### com.GetPointer(COM对象 )

获取 IDispatch 指针

该指针返回前已调�?AddRef 增加 COM 引用计数,

不再使用时必须及时调�?com.Release 释放

### com.GetPointer(COM对象 或指�?GUID)

使用 GUID 指定接口获取原生指针,

该指针返回前已调用AddRef增加COM引用计数,

不再使用时必须及时调�?com.Release 释放,

参数@1可是 COM对象 、com.IUnknown对象、或可转换为指针的对�?
参数@2可用文本格式表示,省略时默认为IID\_IUnknown

### com.GetTypeInfo()

[返回对象:comTypeInfoObject](#comTypeInfoObject)

### com.GetTypeInfo(/\*COM对象 \*/)

返回类型信息

### com.ImplInterface(implObject)

�?aardio 对象转换为支�?IDispatch 接口�?COM对象 �?
参数@1可以是普通表对象、函数对象、类对象、cdata对象�?
如果参数@1是函数或类对�?回调时onwer参数�?dispIdMember 数值�?
如果参数@1是表对象转换�?COM对象 ，直接作�?COM 函数调用时支�?\_call元方法，

如果未定�?\_call元方法则调用表对象中索引�?的函�?
通过 COM 接口调用表的成员函数时支�?\_get 元方法，并将 onwerCall 参数设为 true�?
表对象或表的成员函数作为COM函数回调�?onwer 参数总是指向表对象自�?

dispIdMember小于0时总是调用表索引中对应的函�?

在与 COM 接口交互时，

无法自动转换�?COM对象�?aardio 对象也会调用此函数自动转�?
### com.ImplInterface(implTable,progID,interfaceName)

使用一�?table 表转换为 @interfaceName 指定的接口对�?
例如：com.ImplInterface( flash.callevent ,"ShockwaveFlash.ShockwaveFlash","\_IShockwaveFlashEvents")

### com.ImplInterfaceFromTypelib(implTable,typelibPath,interfaceName,coclassNname)

使用类型库实现com接口

### com.IsIUnknown(任意参数)

检测参数是否一个托�?com.IUnknown 指针

### com.IsMember(comObject,memberName)

返回参数 @memberName 指定的名字是�?@comObject 参数指定 COM 对象的成员�?
### com.IsNetObject(任意对象)

检测参数是否一�?.Net 原生对象，是则返回非 0 值�?
如果是普�?.Net 对象返回 1，如果是 DispatchableObject 对象返回 2

### com.IsObject(任意对象)

检测参数是否一个动�?COM对象（IDispatch 对象�?
### com.LoadTypeLibrary(".tlb")

加载类型�?
参数可以是CLSID、类型库路径、或包含类型库资源的组件路径

### com.LoadTypeLibrary()

[返回对象:comTypeLibObject](#comTypeLibObject)

### com.NewControl(tab,progId)

创建COM控件,可选使用参数@3指定tlb类型库路�?
此函数详细用法请参考标准库com.activeX的源代码

### com.NewObject(tab,progId)

创建COM对象,可选使用参数@3指定tlb类型库路�?
此函数详细用法请参考标准库com.activeX的源代码

### com.QueryObject(IUnknown指针 )

查询 IDispatch 接口、并创建 com.IDispatch 对象

### com.QueryObjectR(IUnknown指针 )

查询 IDispatch 接口、并创建 com.IDispatch 对象

如果成功则调�?com.Release 释放传入�?IUnknown 指针

使其引用计数减一,释放的指针不应再使用,

返回�?COM对象 会增加引用计�?

并在对象释放时自动减一

### com.Release()

释放 COM 对象�?NET 对象、IUnknown 指针、com.interface 创建的对象�?
如果参数 �?pointer 类型指针调用 IUnknown 接口 Release 函数使引用计数减一

如果参数�?cdata 内核对象或自元表中返�?cdata,则调�?cdata �?\_gc 析构函数

参数 @1 �?null 抛出异常

### com.ReleaseConnection(comObject)

释放默认事件监听�?

@comObject 指定要解除事件监听器�?COM对象 ,

默认事件监听器由 com.Connect 函数绑定

即使不调用此函数,

�?COM对象 销毁后所有事件监听器会自动释�?
### com.ReleaseConnection(comObject,eventSink, cookie)

释放事件监听�?

@comObject 指定要解除事件监听器�?COM对象 ,

@eventSink 可以�?com.ImplInterface 创建的事件监听器,

也可以使�?com.Connect 的第一个返回�?
@cookie 来自 com.AddConnection 的返回�?
即使不调用此函数,

�?COM对象 销毁后所有事件监听器会自动释�?
### com.RoundTrip()

将aardio对象转换为COM对象�?
再将�?COM对象 转换为aardio对象

### com.SafeArray(\_VT元素类型)

创建 COM 安全数组�?SAFEARRAY �?

可增加一个或多个参数指定数组成员,

返回的数组兼容普通数�?�?数组@.\_safearray\_type 指定了COM类型�?
COM 函数传入传出 COM 数组均使用此格式,

元素类型不指定时默认为VT\_VARIANT,VT\_VARIANT数组兼容 VBS 数组

类型�?VT\_ILLEGAL 则单个值与数组元素类型均自动设�?这是调用 COM 接口的默认规则�?
纯字符串数组默认元素类型�?\_VT\_BSTR,纯数值类型默认元素类型为 \_VT\_R8（double�?

IDispatch 对象数组元素类型�?\_VT\_DISPATCH�?
其他数组元素类型默认�?\_VT\_VARIANT

### com.SafeArrayType()

如果传入参数�?SafeArray 数组,

返回一个表示数组元素类型的数�?该值应�?_VT_ 前缀的常量进行比�?
支持 com.SafeArray 创建的数�?�?COM 函数返回的数�?

参数如果�?com.SafeArrayV 创建�?SafeArray 数组封装对象,返回 null,

参数如果�?com.Variant 创建�?Variant 对象,返回 null,

参数是其他类型�?也返�?null

### com.SafeArrayV(数组,元素类型)

返回 SAFEARRAY 数组包装对象,

该对象的 \_safearray 属性指向参数传入的数组,\_type 指向数组类型,

注意此函数返回的对象不是 SafeArray 数组，也不会修改传入的数组，

返回对象仅用于在调用 COM 函数时自动转换为 SAFEARRAY 数组�?
参数@1可以是数�?字符�?buffer,也可以指定null值并转换为空数组,

元素类型不指定时默认为VT\_VARIANT,VT\_VARIANT数组兼容 VBS 数组�?
类型�?VT\_ILLEGAL 则单个值与数组元素类型均自动设�?这是调用 COM 接口的默认规�?

纯字符串数组默认元素类型�?\_VT\_BSTR,纯数值类型默认元素类型为 \_VT\_R8（double�?

IDispatch 对象数组元素类型�?\_VT\_DISPATCH�?
其他数组元素类型默认�?\_VT\_VARIANT

### com.SetPreferredArrayType(/\*COM 对象\*/,0xC/\*\_VT\_VARIANT\*/)

设置调用�?COM对象 �?aardio 数组参数�?COM 数组的默认类型，

参数只能设为 \_VT\_VARIANT �?\_VT\_ILLEGAL,默认已设置为 \_VT\_ILLEGAL�?
此设置值会自动传递到�?COM对象 返回的其�?COM对象 �?
此选项设为 \_VT\_ILLEGAL 将自动调整为合适的类型,规则如下�?
纯字符串数组类型设为 \_VT\_BSTR,

纯数值数组类型设�?\_VT\_R8（double），

其他数组类型设为 \_VT\_VARIANT�?
这也是所�?COM对象 的默认设置�?
如果要创建明确指�?COM 类型的数组参数，

可使�?com.Variant,COM.SafeArray,COM.SafeArrayV,com.int...等函�?
### com.ShowHelp(/\*COM对象 \*/)

显示帮助

### com.TryCreateObject(cls,...)

参数可指定一个或多个CLSID/ProgID,逐个测试直到创建成功,

成功返回 com.IDispatch 对象,

创建失败返回null,错误信息,不会抛出异常,

参数@1可指�?CLSID�?ProgID

### com.TryGetObject("字符串参�?)

从已运行的实例获取并返回 com.IDispatch 对象,

参数可指定一个或多个 CLSID/ProgID,也可指定要打开的文件路�?如doc文件,

创建失败返回null,错误信息,不会抛出异常�?
如果当前进程与目�?COM 服务进程不具有相同权限，则会返回 null�?
### com.Variant

创建 VARIANT 变体对象�?
可用于普�?COM对象 传值或传址参数�?
可用�?.NET 普通输入参数，不支�?.NET 输出参数（可改用 dotNet.object）�?
可用�?API 函数�?VARIANT\* 指针类型参数�?
### com.Variant()

[返回对象:comVariantObject](#comVariantObject)

### com.Variant(初始�?变体类型,输出引用)

可选指定一个初始值，可以是任意适用�?COM 参数的值或数组�?
参数 @2 可选用一�?_VT_ 前缀的整数常量指定期望的 COM 变体类型�?
变体类型指定数值，且参�?@1 为无元表的空表或非空数组时都会处理为 COM 数组�?
若省略类型或设为 \_VT\_VARIANT，则单值自动选择类型，未明确类型的数组设�?VT\_VARIANT�?
如果变体类型�?\_VT\_ILLEGAL，则单值与数组均自动选择类型，此�?COM 接口默认规则�?
单整数默认类型为 \_VT\_I4（int�?小数默认类型�?\_VT\_R8（double�?

纯字符串数组默认�?\_VT\_BSTR 数组,纯数值类型默认为 \_VT\_R8（double）数�?

其他数组类型默认�?\_VT\_VARIANT 数组�?
可选参�?@3 如果设为 true，就可以用于 COM 输出参数�?
### com.Variant(指针,true)

创建 VARIANT 变体对象

如果参数@2�?true ，则参数 @1 必须�?VARIANT 指针�?
调用 VariantCopyInd 函数拷贝参数指定的源 VARIANT 对象

### com.byte()

定义数值类型为 8 位整数，

作为输入参数可兼�?.Net System.SByte 类型数值�?
参数 @1 可以为数值或数组�?
参数 @2 �?true 则用�?COM 输出引用参数�?
此函数返�?com.Variant 对象�?
[返回对象:comVariantObject](#comVariantObject)

### com.double()

定义数值类型为 64 位浮点数�?
此函数返�?com.Variant 对象�?
作为输入参数可兼�?.Net System.Double 类型数值�?
参数 @1 可以为数值或数组�?
参数 @2 �?true 则用�?COM 输出引用参数�?
注意普通数值传�?COM 参数时，

整数默认转为32位整数，小数默认按double类型处理

[返回对象:comVariantObject](#comVariantObject)

### com.each

```aardio aardio
for index,obj in com.each() {

} //迭代遍历com集合对象，参数可以直接传入COM迭代�?
```

### com.eachRunning(interface,name)

```aardio aardio
for object,interface,name,index in com.eachRunning() {
    /*遍历ROT（运行对象表�?参数 @interface 可选限定接口名（完全匹配），参�?@name 可选用模式串限定显示名称�?返回 object�?COM 对象 ,interface 为接口名称（可能�?null�?name 为显示名称。index 为序�?/
}

```

### com.enumRunning(回调函数)

```aardio aardio
com.enumRunning(
    function(displayName,object){
        /*枚举ROT（运行对象表）并获取COM对象,
此回调函数返回true中止枚举*/
    }
)

```

### com.first()

对传入的 COM对象 调用 com.each 创建迭代�?

执行该迭代器并返回第一次返回的 COM对象 ,

如果传入参数�?null �?false 则直接返�?
### com.float()

定义数值类型为 32 位浮点数�?
作为输入参数可兼�?.Net System.Single 类型数值�?
参数 @1 可以为数值或数组�?
参数 @2 �?true 则用�?COM 输出引用参数�?
此函数返�?com.Variant 对象�?
### com.int()

定义数值类型为 32 位整数，

此函数返�?com.Variant 对象�?
作为输入参数可兼�?.Net System.Int32 类型数值�?
参数 @1 可以为数值或数组�?
参数 @2 �?true 则用�?COM 输出引用参数�?
注意普通数值传�?COM 参数时，

整数默认转为32位整数，小数默认按double类型处理

[返回对象:comVariantObject](#comVariantObject)

### com.isEnumerator(对象)

检查并返回参数指定的对象是�?COM 迭代�?
### com.long()

定义数值类型为 64 位整数，

作为输入参数可兼�?.Net System.Int64 类型数值�?
参数 @1 可以为数值或数组�?
参数 @2 �?true 则用�?COM 输出引用参数�?
此函数返�?com.Variant 对象�?
[返回对象:comVariantObject](#comVariantObject)

### com.ubyte()

定义数值类型为 8 位无符号整数，兼�?.Net System.Byte 类型数值�?
参数 @1 可以为数值或数组�?
参数 @2 �?true 则用�?COM 输出引用参数�?
此函数返�?com.Variant 对象�?
[返回对象:comVariantObject](#comVariantObject)

### com.uint()

定义数值类型为 32 位无符号整数�?
作为输入参数可兼�?.Net System.UInt32 类型数值�?
参数 @1 可以为数值或数组�?
参数 @2 �?true 则用�?COM 输出引用参数�?
此函数返�?com.Variant 对象�?
[返回对象:comVariantObject](#comVariantObject)

### com.ulong()

定义数值类型为 64 位无符号整数�?
作为输入参数可兼�?.Net System.UInt64 类型数值�?
参数 @1 可以为数值或数组�?
参数 @2 �?true 则用�?COM 输出引用参数�?
此函数返�?com.Variant 对象�?
[返回对象:comVariantObject](#comVariantObject)

### com.uword()

定义数值类型为 16 位无符号整数，兼�?.Net System.UInt16 类型数值�?
参数 @1 可以为数值或数组�?
参数 @2 �?true 则用�?COM 输出引用参数�?
此函数返�?com.Variant 对象�?
[返回对象:comVariantObject](#comVariantObject)

### com.word()

定义数值类型为 16 位整数，

作为输入参数可兼�?.Net System.Int16 类型数值�?
参数 @1 可以为数值或数组�?
参数 @2 �?true 则用�?COM 输出引用参数�?
此函数返�?com.Variant 对象�?
[返回对象:comVariantObject](#comVariantObject)

## comEnumeratorObject 成员列表

### comEnumeratorObject.Clone()

复制对象

[返回对象:comEnumeratorObject](#comEnumeratorObject)

### comEnumeratorObject.Next(n)

向后获取并返�?n 个元素的�?
### comEnumeratorObject.Reset()

重置到开始位�?
### comEnumeratorObject.Skip(n)

跳过 n 个元素的�?成功返回 true

## comTypeAttrObject 成员列表

### comTypeAttrObject.Funcs

函数总数

### comTypeAttrObject.GUID

```aardio aardio
GUID

```

### comTypeAttrObject.ImplTypes

实现接口总数

### comTypeAttrObject.Vars

属性值总数

### comTypeAttrObject.typekind

类型,

值为"coclass","enumeration","interface","dispinterface"

"alias","union","record","module"之一

## comTypeAttrObject.flags 成员列表

### comTypeAttrObject.flags.appobject

```aardio aardio
appobject

```

### comTypeAttrObject.flags.cancreate

```aardio aardio
cancreate

```

### comTypeAttrObject.flags.control

```aardio aardio
control

```

### comTypeAttrObject.flags.dispatchable

```aardio aardio
dispatchable

```

### comTypeAttrObject.flags.hidden

```aardio aardio
hidden

```

### comTypeAttrObject.flags.oleautomation

```aardio aardio
oleautomation

```

## comTypeDocObject 成员列表

### comTypeDocObject.helpstring

对象的描�?
### comTypeDocObject.name

对象接口名称

## comTypeFuncObject 成员列表

### comTypeFuncObject.Params

参数数量

### comTypeFuncObject.ParamsOpt

可选参数数�?
### comTypeFuncObject.description

描述

### comTypeFuncObject.dispatchable

是否动态接口函�?
### comTypeFuncObject.helpcontext

数值，帮助上下�?
### comTypeFuncObject.helpfile

帮助

### comTypeFuncObject.invkind

调用类型

可能的值为"\_get","\_set","\_setByRef","function"

### comTypeFuncObject.memid

成员ID

### comTypeFuncObject.name

函数�?
### comTypeFuncObject.restricted

是否不适合动态调�?
### comTypeFuncObject.type

返回值类型，字符�?
### comTypeFuncObject.vt

返回值类型，数�?

数值含义与 com.Variant 对象�?vt 字段相同

## comTypeFuncObject.parameters 成员列表

参数描述数组

### comTypeFuncObject.parameters.?

[返回对象:comTypeParameterObject](#comTypeParameterObject)

## comTypeInfoObject 成员列表

### comTypeInfoObject.DumpTypeInfo()

返回一个字符串,

列出此类型所有的成员

### comTypeInfoObject.GetDocumentation()

返回文档信息

[返回对象:comTypeDocObject](#comTypeDocObject)

### comTypeInfoObject.GetFuncDesc()

[返回对象:comTypeFuncObject](#comTypeFuncObject)

### comTypeInfoObject.GetFuncDesc(索引)

返回函数描述

注意超始索引�?

### comTypeInfoObject.GetImplType()

[返回对象:comTypeInfoObject](#comTypeInfoObject)

### comTypeInfoObject.GetImplType(索引)

返回实现接口

注意超始索引�?

### comTypeInfoObject.GetImplTypeFlags(索引)

实现接口类型属性表

返回表包含字段default,source,restricted,defaultVTable,都是布尔�?

注意超始索引�?

### comTypeInfoObject.GetTypeAttr()

返回类型属�?
[返回对象:comTypeAttrObject](#comTypeAttrObject)

### comTypeInfoObject.GetTypeLib()

返回类型�?
[返回对象:comTypeLibObject](#comTypeLibObject)

### comTypeInfoObject.GetVarDesc(索引)

COM变量/常量描述

注意超始索引�?

## comTypeLibObject 成员列表

### comTypeLibObject.ExportConstants()

导出常量名值对组成的表�?
可以使用常量名作�?COM 对象的成员名获取常量�?
### comTypeLibObject.ExportEnumerations()

导出全部枚举类型�?
返回一个表，键为枚举类型名，值为该类型的枚举名值对组成的表�?
通常枚举名值对也是 COM 常量名值对�?
可以使用枚举名字（不用指定枚举类型名�?
作为 COM 对象的成员名获取枚举�?
### comTypeLibObject.GetDocumentation()

返回文档信息

[返回对象:comTypeDocObject](#comTypeDocObject)

### comTypeLibObject.GetTypeInfo()

[返回对象:comTypeInfoObject](#comTypeInfoObject)

### comTypeLibObject.GetTypeInfo(索引)

返回类型信息

注意超始索引�?

### comTypeLibObject.GetTypeInfoCount()

类型信息总数

### comTypeLibObject.ShowHelp()

显示帮助

## comTypeParameterObject 成员列表

### comTypeParameterObject.default

参数的默认�?
### comTypeParameterObject.in

是否输入参数

### comTypeParameterObject.opt

是否可选参�?
### comTypeParameterObject.out

是否输出参数

### comTypeParameterObject.type

参数类型，字符串

### comTypeParameterObject.vt

参数类型，数�?

数值含义与 com.Variant 对象�?vt 字段相同

## comTypeVarObject 成员列表

### comTypeVarObject.name

COM变量�?
### comTypeVarObject.value

COM常量�?
## comVariantObject 成员列表

### comVariantObject.bstrVal

只读属�?获取BSTR指针

### comVariantObject.clear()

清空�?
调用VariantClear函数清空值并重新初始化对�?
调用了此函数以后,对象的vt置为0�?
其他所有成员置为null，包括clear函数也置为null�?
除非通过value属性重新赋�?clear函数才会变为可用

即使不调用这个函数，

aardio在析构回收对象时也会自动调用VariantClear函数释放资源

### comVariantObject.parray

只读属�?获取SAFEARRAY指针

### comVariantObject.pdispVal

只读属�?获取IDispatch指针

### comVariantObject.punkVal

只读属�?获取IUnknown指针

### comVariantObject.value

读写值遵守com与aardio间的数据类型转换规则

### comVariantObject.vt

Variant类型，数值，

只读属性，不可修改

## embedObject 成员列表

### embedObject.\_form

COM 对象的容器窗口�?
这是一�?win.form 对象或�?win.form 对象内部的控件对象�?
[返回对象:staticObject](../win/ui/ctrl/static.html#staticObject)

### embedObject.\_object

原生 COM 控件对象�?
原生 COM 控件对象不等于事件监听表，一般不用于直接绑定 COM 事件�?
应当�?com.Connect 绑定事件监听表�?
CreateEmbedEx �?CreateEmbed 返回的容器对象也可自动绑�?COM 事件�?
## embedObject.\_host 成员列表

COM 控件宿主对象�?
提供部分 OLE 接口函数，一般没必要直接使用这个对象�?
### embedObject.\_host.\_adjust()

自动调整控件窗口大小

### embedObject.\_host.close()

关闭

### embedObject.\_host.doObjectVerb( \_OLEIVERB )

执行指定的动词命�?
### embedObject.\_host.tranacc(MSG消息对象)

解析快捷�?

如果是快捷键返回真�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/builtin/com.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/builtin/com.md')

