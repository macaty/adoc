[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# 数据类型

## aardio 数据类型

- null 空�?[#](#null)

  null 表示空值、未定义的值。所有变量默认初始值为 null �?
  null 表示没有存储任何数据，将一个变量赋值为 null 等于删除这个变量�?
  地址�?0 的指针值为 null ，任何时候写 topointer(0) 是多余无意义的�?
  调用函数时，留空的调用参数等价于�?null 参数。例�?`console.log(1, ,3)` 等价�?`console.log(1,null,3)` �?
- boolean 布尔值�?[#](#boolean)

  只有 true, false 两种值的逻辑数据类型。true 表示真，false 表示假�?
  布尔值通常用在条件表达式中�?

  通俗一点说，true 表示是、符合条件，false 表示不是、不符合条件�?
  在条件表达式(恒等式除�?中， null、数�?0 等价�?false�?�?false　�?null �?0 的其他值为 true�?
  �?aardio 的文档中如果一个函数返回值的用途被描述为“是�?……�?或相同语义的类似说明，即说明该函数应该返回一个布尔值，不再额外作出说明�?
  如果一个函数返回布尔值，那么该函数默认可以返回任意类型的�?\- 不会再额外说明。任意类型的值可按非 false　�?null �?0 值为 true 的规则自动转换为布尔值使用，不再额外作出说明�?
  如果函数文档有特别说明，函数也可以区�?null, false, 0 等不同返回值以表示不同语义�?
  注意在原生数据类型中布尔值转换为 32 位整数（ 零为 flase，非零为 true ）�?
- number 数�?[#](#number)

  aardio 中的 数值默认存储为 64 位浮点数（即原生类型中的 double 类型）�?
  数值也可以使用不同的进制来表示，参考： [数值与进制](number.html) 。可使用 `0x` 前缀表示十六进制数，例如 `var num = 0xA1 + 0xFF`。使�?`2#` 前缀可以表示 2 进制数，使用 `8#` 前缀可以表示 8 进制数�?
  �?aardio 中也可以用科学计算法表示数值，例如�?`var num = 6e+20`�?

  > 科学计数法：科学计数法也�?10 的幂计数法。把一个大�?10 或小�?1 的数记为 `a * 10n` 的形式，其中 a 称为尾数、n 称为指数，a 是整数位只有一位的数，然后�?E �?e 来表�?10 的幂。例�?x= -3.5×105 这里 -3.5 是尾数，指数�?5，我们可以将它表示为-3.5E5�?

  数值的字面值允许加入下划线作为数值分隔符，例�?`123_456` 等价�?`123456`�?`2#1010_1100` 等价�?`2#10101100`�?数值分隔符不能使用连续多个下划线。只能在 aardio 代码中使用数值分隔符，不能在字符串中使用数值分隔符。例�?`tonumber("123_456")` 返回的是 123 ，�?`("123_456") + 1` 则会报错�?
  在与原生 API 交互时，aardio 支持将数值转换为各种位长的有符号与无符号数、双精度浮点数、单精度浮点数，在原�?API 函数中如果未加类型声明则 aardio 数值默认转�?32 �?int 类型�?
  aardio 提供 math.size64() 函数用于 创建 64 位无符号整数（数据类型为 cdata，兼容原生数据类型中�?LONG 类型）�?
  示例�?

  ```aardio aardio
  var num = 123;
  var size64 = math.size64(123);

  ```

- string 字符�?[#](#string)

  请参�?[《字符串与编码》](string.html)

  aardio 字符串可以包含二进制数据，也可以包含文本，文本字符串的默认编码为 UTF 编码�?
  字符串指向的内存是只读的字节数组，可用下标读取每个字节的 8 位无符号数值（但不可写入）�?任何对字符串的修改都会返回新的字符串（而非修改原来的内存）�?
  在调用原�?API 函数时可作为只读的字符串指针参数使用。aardio 字符串尾部总是会保护性地放置2个隐藏的字节'\\0\\0'（不计入字符串长度，不包含在字符串中）， 因此 aardio 字符串可兼容 C 风格字符串�?
  使用双引号或反引号包含的字符串为原始字符串，不处理转义符�?
  使用单引号包含的字符串可处理转义符�?
  示例�?

  ```aardio aardio
  var str1 = `原始字符串`;
  var str2 = "原始字符�?;
  var str3 = '转义字符�?;

  ```


  注释也可以赋值为字符串，示例�?

  ```aardio aardio
  var str1 =  //注释字符�?
  ```

- buffer 可读写字节数组（缓冲区） [#](#buffer)

  buffer 是使�?raw.buffer() 函数分配的可读写、固定长度的内存，用于存取各种二进制数据�?
  可用下标操作�?`[]` 读写内存中指定索引的字节码（ 8 位无符号数�?）。可以用 # 操作符取字节数组长度�?不支持连接操作符，但支持调用 raw.concat,string.concat,string.join 等函数以不同方式拼接�?
  buffer 在几乎所有字符串函数中都可以作为字符串使用。在结构体中也可作为指针�?`BYTE []` 数组的值。在原生 API 参数中可作为内存指针、字符串、输出字符串使用。在 COM 函数中可作为安全数组使用�?
  注意 ![](../../icon/info.gif)�?  如果在一个结构体中，�?buffer 赋值为一个结构体的指针字段，并将这个结构体作为输出参数调�?API�?�?API 函数返回以后，只要指针地址没有改变 —�?则这个字段的值仍然是指向原来�?buffer 对象�?如果指针地址被修改，则会变为新的指针�?）�?
  buffer �?json 中会转换�?`{type="Buffer";data={} }` 格式的表对象。这种表对象可作�?raw.buffer() 函数的唯一参数还原�?buffer 对象�?
  buffer 尾部总会保护性地放置2个隐藏的字节 `'\0\0'`（不计入字符串长度，不包含在字符串中）�?与动态指针不同的是，即使你不指定初始值，aardio 仍然会初始化 buffer 中所有字节的值为0，buffer 的长度是不可变的�?请参�? [raw.buffer 函数](../../library-guide/builtin/raw/mem.html)

  如果�?buffer 指定 [元表](table/meta.html)，则 buffer 对象会转换为 cdata 对象，并且也不能再作�?buffer 对象使用�?
- table �?
  请参�?[《表》](table/_.html)

  aardio 中唯一的复合数据类型就�?table�?  table 可包含哈希表、数组成员，也可以用于定义结构体�?
- function 函数

  函数是预定义的子程序，用于封装一段可复用的代码，可以接受零个或多个参数，返回零个或多个值�?
  使用 function 关键字定义函数，使用 `()` 操作符调用函数。请参考： [定义函数](../function/definitions.html)

- class �?
  类用于动态创建数据结构相同的实例对象�?
  使用 class 关键字定义类，请参考： [class](../class/class.html)

- fiber 纤程

  调用 fiber.create() 创建并返回纤程对象�?纤程类似线程，但不是线程。纤程有独立的运行堆栈，并且也可以暂停或继续运行，但是纤程并不会创建新的线程，也不能同时运行多个纤程�?
  请参考《库函数文档》： [《内置库 / 纤程》](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/fible/md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ������������ļ�δ�ҵ���  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/fible/md')

- cdata 内核对象

  aardio 内核对象，例�?math.size64, [io.file](../../library-guide/builtin/io/file.html) 对象�?
- pointer 指针 [#](#pointer)

  内存指针一般用于存储内存地址.但有时候也可能用于存储句柄地址或者无效的内存地址，内存指针给你最大的自由，同时也带来最大的风险，应谨慎使用�?
  - 动态指针：

    动态指针是一种特殊的指针�?
    raw.realloc() 函数可用于分配、释放一个动态指针，也可以使�?raw.realloc() 重新调整动态指针分配的内存大小，动态指针的地址是可变的，调整大小后应废弃旧的指针地址并更新为 raw.realloc() 返回的新指针�?
    示例�?

    ```aardio aardio
    //分配 10 字节长度的内存，返回动态指�?    var ptr = raw.realloc(10);

    //调整内存大小
    ptr = raw.realloc(20,ptr);

    ```


    动态指针会在返回给用户的指针地址前面倒退8个字节记�?�?2位字段的内存长度、数据长度信息，然后总是向后移动8个字节将可用的指针地址返回给用户， 动态指针尾部总会保护性地放置2个隐藏的字节'\\0\\0'（不计入内存长度，不包含在存储数据中）�?
    �?buffer 不同的是，如果不指定初始化值，raw.realloc 就不会对分配的内存设定初始化值， 并且 aardio 不负责自动释放动态指针分配的内存，显式的调用 `raw.realloc(0，动态指�?` 才能释放一个动态指针�?
    动态指针可以作为普通内存指针使用，也可以用于支持动态指针的 raw.realloc() raw.concat() raw.sizeof() 等函数�?
    可使�?raw.sizeof() 获取动态指针指向内存的大小�?    �?raw.concat() 函数可以对动态指针的内存追加拼接数据�?
    要记住这些操作动态指针的函数不要误传不是�?raw.realloc() 分配的非动态指针进去，aardio 不会检查或阻止这种错误操作�?
## 数据类型转换 [\#](\#type-conversion)

### 显式类型转换

aardio 提供以下转换类型的函�?
- tostring(v) 转换参数v为字符串，可使用 `_tostring` 元方法自定义转换函数。要注意 aardio 中一些操作字符串的函数会自动调用 tostring 将参数转换为字符串（ 函数说明必须明确提到对参数调用了 tostring 函数 ），例如 `console.log()` 就会这样做�?- tonumber(v) 转换参数v为数值，忽略首尾空白字符，可使用 `_tonumber` 元方法自定义转换函数�?- topointer(v) 转换参数 v 为指针，可使�?`_topointer` 元方法自定义转换函数。地址�?0 的指针值为 null ，任何时候写 topointer(0) 都是多余无意义的�?
示例�?
```aardio aardio
//转换一个变量为数字，如果失败返�?null 空�?var n = tonumber( "2" );

//转换一个变量为字符串，如果失败返回 null 空�?var str = tostring( 2 );

//转换为指针，如果失败返回 null 空�?var ptr = topointer( 123 );

```

另外，使�?个逻辑非操作符可以将任何值转换为布尔值，例如:

```aardio aardio
var num = !!0;

```

### 隐式数据类型转换 [\#](\#type-coercion)

aardio 也允许数据类型自动转换，规则如下:

1. 在逻辑运算中，�?0\. �?null、非 false 值为 true，反之为 false�?
2. 使用 [等式运算符](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/language-reference/datatype/..operatorequality.html  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ������������ļ�δ�ҵ���  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/language-reference/datatype/..operatorequality.html') 比较 2 个值时�?
   - 任意值与 true,false 比较则先转换为布尔值�?
   - 非布尔值与数值比较，则先转换为数值，然后比较数值是否相等�?
     例如 `null == 0` 就属于非布尔值与数值比较，�?null 转换为数值还�?null，null �?0 不是相等的数值。所�?`null == 0` 会返�?false �?
     再例�?`""== 0` �?`' \t\r\n'== 0` 同样属于非布尔值与数值比较，空白字符串自动转换为数值时返回 0，所�?`""== 0` �?`' \t\r\n'== 0` 都会返回 true�?3. 在算术运算、以�?math 库函数里无特别说明的数值参数都支持字符串自动转换为数值，转换失败则抛出异常。其他内置库、标准库函数一般都支持字符串自动转换为数值，有特别说明或对参数类型有特别要求的除外�?
   字符串在自动转换为数值时，忽略首尾空白字符，空白字符串会转换�?0，�?tonumber 函数会将空白字符串转换为 null。而且 tonumber 函数会调�?`_tonumber` 元方法，但自动转换数据类型时并不会调�?`_tonumber` 元方法�?
   示例:


   ```aardio aardio
   import console;
   console.log( ("") + ('\r\n\t ') + 0 ); //显示 0
   console.log( tonumber("") === null ); //显示 true
   console.pause(true);

   ```


   通常用于检测参数类型的函数会明确区分字符串与数值，例如 math.isInteger() 函数�?检测与区分参数类型的原�?API 函数、COM 函数也会明确区分字符串与数值�?
4. 在字符串连接操作时，数值会自动转换为字符串�?
   要特别注意字符串的字面值两侧的 \+ 会自动转换为 ++�?

   例如 "1" + 0 会自动转换为 "1" ++ 0 做字符串连接操作，但 ("1") + 0 会执行加法运算�?

### 函数参数或对象属性的类型转换

除非文档有特别说明，函数参数（或对象属性）应使用准确的类型�?
少量函数（或对象属性）会支持可兼容的类型转�?—�?如果文档没有特别说明这一点，调用者不应当依赖这种转换（除非函数文档中有明确说明支持相应转换）�?
过多地依赖类型转换是不必要的 —�?使用准确的类型是更好的选择�?
### 原生数据类型中的类型转换

请参考：

- [原生数据类型](../../library-guide/builtin/raw/datatype.html)

- [不声明调�?API](../../library-guide/builtin/raw/directCall.html)


## 使用 type 函数获取数据类型 [\#](\#type)

1. 函数原型�?
   `var dataType[，structType][，metaType] = type( any )`

2. 函数说明�?
   type 函数返回对象的基本数据类�?dataType�?

   如果对象是一�?struct 结构体，则返回结构体类型 structType�?

   如果对象在元表中指定�?`_type` 字段的值，则返回元类型 metaType�?
   aardio 用字符串描述类型，所以返回的类型都是字符串，


   如果没有任何参数，type 函数无返回值（ 也就是返�?null �?）�?
3. 调用示例�?

   ```aardio aardio
   import console;

   //显示null , null
   console.log( type(null) , type.null );

   //显示 string , string
   console.log( type("Hello world") , type.string );

   //显示 number , number
   console.log( type(1000) , type.number );

   //function , function
   console.log( type(console.log) , type.function );

   //显示 class , class
   console.log( type( class{} ) , type.class );

   //boolean , boolean
   console.log( type(true) , type.boolean );

   //显示 cdata , cdata
   console.log( type( io.stdin ) , type.cdata );

   //显示 table , table
   console.log( type( {x=0;y=0} ) , type.table );

   //显示 pointer , pointer
   console.log( type( topointer( 1 ) ) , type.pointer );

   console.pause();

   ```


## 使用 type.eq 比较数据类型

1. 函数原型�?
   `var eq = type.eq( obj，obj2 )`

2. 函数说明�?
   比较参数 obj、参�?obj2 的类型、元类型、struct类型，如果完全相等返回true，否则返回false�?
   请注意在 aardio 中如果一个函数说明会返回布尔�? true，false) ，如果未加特别说明则允许返回任何可自动转换为布尔值的其他数据类型的值�?例如 type.eq() 可能会返�?null 值以替代 false，aardio 中的函数说明不再重复说明此类自动类型转换规则�?
3. 调用示例:


   ```aardio aardio
   import console;
   import time.ole;

   var tmOle = time.ole();
   var tm = time();

   //type.eq 严格比较所有类�?基础类型、元类型、struct类型)
   if( type.eq( tmOle,tm ) ){
       console.log("tmOle,tm 类型相同")
   }
   else{
       console.log("tmOle,tm 类型不相�?)
   }

   //time.istime 不比较元类型,因此兼容 oletime
   console.log( "�?time 对象�?",time.istime(tmOle) )

   console.pause();

   ```


[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/language-reference/datatype/datatype.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/language-reference/datatype/datatype.md')
