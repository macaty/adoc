[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# com 库使用指�?
COM 具有与语言，平台无关的特性，aardio提供 com 库对 COM 组件提供支持�?
## 引用 com �?
com 虽然是内置库，但�?aardio 中默认是不加载的，在使用前必须调�?import 语句导入 com 库�?
```aardio aardio
import com; //载入 com �?
```

## com.CreateObject

1. 函数原型�?
   `comObject = com.CreateObject( progID )`

2. 函数说明�?
   progID 参数指定控件的注册类名，也可以是 CLSID，如果是 CLSID 则必须置于大括号�?

   请参�? [CLSID与ProgID](base.html#id)

3. 函数示例�?

   ```aardio aardio
   import com; //引用com�?   var xml = com.CreateObject("MSXML.DOMDocument") //使用ProgID 创建 COM 对象

   var xml = com.CreateObject("{2933bf90-7b36-11d2-b20e-00c04f983e60}") //使用 CLSID 创建com对象

   ```


## com.GetObject

1. 函数原型�?
   `comObject = com.GetObject( progID )`

2. 函数说明�?
   返回已运行的 COM 对象


   progID 参数指定控件的注册类�?也可以是 CLSID ,如果�?CLSID 则必须置于大括号�?

   请参�? [CLSID与ProgID](base.html#id)

3. 函数示例�?

   ```aardio aardio
   var excel = com.GetObject("Excel.Application")
   var excel =com.GetObject("e:\\SAMP.XLS") //打开指定的文�?
   ```


## com.QueryObject

1. 函数原型�?
   `comObject = com.QueryObject( comObjectPointer )`

2. 函数说明�?
   参数 @comObjectPointer 可以一�?IUnknown 指针对象、也可以是一个普通的pointer 类型指针，函数查询并返回 com.IDispatch 对象�?

## com.ShowHelp

1. 函数原型�?
   `com.ShowHelp( comObject  )`

2. 函数说明�?
   查看帮助

3. 函数示例�?

   ```aardio aardio
   import com; //引用 com �?
   var conn =   com.CreateObject("ADODB.Connection"); //创建数据库连�?   assert(conn,"创建数据库连接时遇到错误");

   com.ShowHelp(conn);   //打开ADO帮助文档

   ```


## com.DumpTypeInfo

1. 函数原型�?
   `com.DumpTypeInfo( comObject  )`

2. 函数说明�?
   在控制台窗口显示类型信息.

3. 函数示例�?

   ```aardio aardio
   import com; //引用com�?
   var xml = com.CreateObject("MSXML.DOMDocument")
   com.DumpTypeInfo(xml)  //输出xml对象的类型信息、成员属性、成员方法列�?
   ```


   console.dump 函数支持�?COM 对象自动调用 com.DumpTypeInfo 函数在控制台输入 COM 对象信息�?
   示例�?

   ```aardio aardio
   import console;

   var xml = com.CreateObject("MSXML.DOMDocument")
   console.dump( xml );

   console.pause();

   ```


### 访问 COM 对象属�?
�?com 对象后面加对象成员操作符 `.` ，然后写属性名称�?
例如�?
```aardio aardio
import com; //引用com�?
var conn = com.CreateObject("ADODB.Connection"); //创建数据库连�?conn.ConnectionString = "Provider=Microsoft.Jet.OLEDB.4.0;Data   Source=test.mdb"

```

## COM 对象 - 读写属性、调用成员函�?
首先看一个简单的示例�?
```aardio aardio
import com; //引用com�?
//创建 COM 对象
var conn = com.CreateObject("ADODB.Connection");

//读写 COM 对象成员属�?conn.ConnectionString = "Provider=Microsoft.Jet.OLEDB.4.0;Data Source=test.mdb"

//调用 COM 对象成员函数
conn.Open();

```

需要注�?COM 对象的同一个成员属性名字，即可以作为一个属性名来获取对应的�? DISPATCH\_PROPERTYGET )，也可以作为一个函数来调用�?DISPATCH\_PROPERTYGET \| DISPATCH\_METHOD ）�?
aardio 会自动识别你的代码，如果使用的是 `.` 成员操作符，并且紧接一个函数调用。例�?`comObj.name();` 这时�?aardio �?comObj.name 作为一个函数并调用该函数�?
如果改用其他获取属性的写法，例如：

```aardio aardio
var name = comObj["name"];
var name = comObj.name;

```

这样就会直接获取 COM 对象原本的属性值，而不是像调用 `comObj.name()` 那样会返回一个函数对象并且调用该函数对象�?
COM 对象的属性通常会支持以上两种写法。例如属�?ele.innerHTML 返回一个字符串，而ele.innerHTML() 以函数调用的方法同样返回字符串�?
COM 对象的文本属性可以使�?UTF16 �?UTF8 编码的字符串赋�?- 即该字符串的 UTF 标记�?16 �?8。也可以在成员名字后面添�?Utf16"后缀访问 UTF-16 编码的文本属性，例如�?ele.innerTextUtf16 获取 ele.innerText，这时候会返回一�?UTF-16 字符串（ustring），注意这种方式获取文本不能写为 ele.innerTextUtf16()�?
也可以成员名字前面添�?get"�?set"前缀,这时�?aardio 会保证返回一个函数，get 前缀返回一个用于读取属性的函数 ,�?set 前缀返回一个用于写入属性的函数�?
```aardio aardio
//comobj是一�?COM 对象

comobj.setText( "文本" ) //等价�?comobj.Text = "文本"

var txt = comobj.getText(); //等价�?txt = comobj.Text

```

�?aardio 实现�?COM 对象不允许（也不必要）使�?get,set 前缀读写属性�?
aardio 实现�?COM 对象�?comObj.name 格式读取不存在的属性返�?null 而不报错，但�?comObj.name() 格式读取 null 值属性时会抛异常（找不到成员）。非 aardio 实现�?COM 对象通常也不建议使用 comObj.name() 格式读取可能�?null 值的属性�?
## COM 对象 - 数值索引成�?
COM 对象有两种使用数值索引获取成员的方法.

其一是像 aardio 一样使�?`[]` 索引操作符，例如 `val = comobj[2]`;

另外一种很常见的方式是使用 `()` 操作符，以函数调用的形式获取成员�?例如:

```aardio aardio
comobj.item(0).Text="testitem"

```

如果 item 是默认属性，有些 COM 对象可以直接写为�?
```aardio aardio
comobj(0).Text="testitem"

```

不同 COM 对象对数值索引的处理可能有所区别，具体就查看文档或者都试一下�?
如果�?COM 对象返回的安全数组，这实际上�?com.SafeArray 对象，也就是声明了一个声明了 \_safearray\_type 元属性的普通数组，数作这种数组的方法与操作普�?aardio 数组一样，简单方便这里不多讲�?
## COM 对象 - 枚举集合对象

如果 COM 对象是一个集合对象并且支持枚举接口，则可以使�?com.each() 创建迭代器来遍历所有数组成员�?
示例:

```aardio aardio
......此处的代码请参考本页开始的示例

// 获取所有的地区标签
var 地区 = xml.getElementsByTagName("地区");

for index, �?in com.each( 地区) {

    //获取市标�?    var �?= �?getElementsByTagName("�?);
    console.log( "�?Id: ",�?item(0).attributes.item(0).nodeValue );
    console.log( "�?value: ",�?item(0).text );
    console.log( "�?Id: ",�?item(1).attributes.item(0).nodeValue );
    console.log( "�?value: ",�?item(1).text );
}

```

## 获取 com.IUnknown 对象

1. 函数原型�?
   `unknowData = com.GetIUnknown( com对象 |com.IUnknown对象|pointer指针 )`

2. 函数说明�?
   返回 COM 对象�?com.IUnknown 内核对象( type.cdata 对象 ) .


   com.IUnknown 内核对象已定�?\_gc 元方�?可自动管理引用计数自动释放�?com.IUnknown 内核已定�?\_topointer 元方�?�?API 函数参数中可自动转换为普�?pointer 指针.

   如果参数是一�?com.IUnknown 内核对象,�?com.GetIUnknown 直接返回该对�?

   如果参数是一个普通的 pointer 裸指�?则com.GetIUnknown将此指针封装�?com.IUnknown 内核对象.


   注意,你必须确�?pointer 指针的确是一�?IUnknown 指针,并承担误用非 IUnknown 指针的风�?


   实际�?使用pointer类型的指针总是有较大的风险、指针很快很自由，但是需要你有高超的技术�?

## 获取IUnknown指针

1. 函数原型�?
   `指针 = com.GetPointer( com.IDispatch对象 )`

2. 函数说明�?
   返回com对象的IUnknown裸指�?该函数会自动调用对象的AddRef()函数增加引用计数.


   裸指针不会自动释�?必须显式调用 com.Release() 函数释放.

   com.GetPointer 返回的是原生裸指�?必须由你自已小心的控制引用计�?你必须熟�?COM 引用计数的规�?


   忘记调用com.Release(),或调用com.Release()释放已释放的指针都会导致com对象引用计数错误,并导致错语的释放操作.


## 自动释放 COM 对象

com.IDispatch对象、com.IUnknown 对象都会在不再存在任何引用时自动释放�?
可以显式启动内存回收进行自动释放，如�?

```aardio aardio
import com;

conn = com.CreateObject("ADODB.Connection"); //创建数据库连�?conn.ConnectionString =  "Provider=Microsoft.Jet.OLEDB.4.0;Data   Source=test.mdb"
conn.Open();//打开数据�?
conn.close();//关闭数据库，首先调用com对象自已的关闭、释放函�?
conn = null; //删除所有引用该对象的变�?
// 下面这句可以省略，垃圾回收器会在需要的时候自动执�?collectgarbage(); //执行垃圾回收，如果没有变量引用该对象，对象被安全删除

```

一般不建议这样去改变内存回收器的运作，更好的方式是让内存回收器自动运行�?
COM 对象会自动回收，一般不必要去主动回收�?
如果需要提前释�?COM 对象，更好的方式是调�?com.Release 函数�?
## 提前释放 COM 对象

1. 函数原型�?
   `指针 = com.Release( pointer指针 | com.IUnknown对象 | com.IDispatch对象 )`

2. 函数说明�?

   COM对象不再使用时会�?aardio 自动销毁，一般不需要手动去释放对象，但也可以显式的调用 com.Release 安全的释�?COM 对象(com.IDispatch 对象）或�?com.IUnknown 对象。对 com.IDispatch 对象�?com.IUnknown 对象重复调用 com.Release 会被忽略�?
   但如果参数是一�?pointer 类型 IUnknown 指针，那么每次调�?com.Release 函数，COM 对象指针�?COM 引用计数都会减一，你必须严格遵守 COM 引用计数规则，如果参数不是一个真正的 IUnknown 指针，或者没有正确的�?COM 规则释放都会导致问题，对这种底层指针误操作可能直接导致程序崩溃�?
   com.GetPointer(对象或指�? 的作用与 com.Release 相反。com.GetPointer 函数会返�?COM 的原生指针、并增加 COM 引用计数�?

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-guide/builtin/com/com.md)

