[aardio 文档](../index.htm "aardio 编程语言文档首页")

# aardio 基本语法

## 数据类型

基本数据类型的详细说明请参考： [数据类型](datatype/datatype.html)

## 标识�?
标识符是�?aardio 中由起标识作用的英文字母、数字或中文字符、以及下划线组成的命名符号， 一般用来标识用户或系统定义的数据或方法，例如常量名、变量名、函数名、类名、名字空间等�?
aardio 标识符基本规则：

- 标识符由英文字母、中文字符、数字、下划线 `_` 三种字符组成�?- 标识符区分大小写�?- 数字不允许作为首字符�?- 首字符为下划线且长度大于 1 个字节、小�?256 个字节的标识符表�?[常量](variables-and-constants.html#constants)，单个下划线符号仍然表示变量�?- 标识符包含中文时，中文字符前面不能有字母或数字�?- 可以使用美元符号 `$` 作为标识符的第一个字符�?
aardio 根据标志符查�?命名对象"的顺序依次为�?
1. 当前 [语句块](statements/blocks.html) 局部变量�?2. 在上层语句块就近搜索 [局部变量](variables-and-constants.html#var) 部变量�?3. 如果有外层函数则继续向上就近搜索所有外�?[函数](function/definitions.html) 的局部变量�?4. 搜索当前 [名字空间](namespace.html)( `self` )的成员变量�?
要特别注意：

> 如果当前名字空间不是全局名字空间，aardio 默认不会到全局表查找命名对象，除非标识符指向一个全局有效的命名对象（全局常量、保留常量、保留函数名）或使用 `..` 操作符明确指定仅在全局表中查找命名对象 �?
## 关键�?
aardio 语法系统保留的关键字，关键字在代码编辑器默认显示为蓝色高亮样式。aardio全部关键字如�?

- var 用于定义局部变�?
- null 用于表示空�?- and not or 逻辑运算�?- false true 用于表示布尔�?- if else elseif 用于条件判断语句
- select case 用于条件判断语句
- for in 用于循环语句
- while do 用于循环语句
- break continue 循环中断语句
- try catch 用于捕获异常
- class ctor 用于创建�?- function 用于创建函数
- lambda 用于创建 lambda 表达�?- λ 等价�?lambda 关键字，�?aardio 中可�?`lambdaλ` 模板输入此符�?- return 用于在函数内返回�?- begin end 用于包含语句�?- namespace 用于创建或打开名字空间
- import 用于引用�?- with 用于打开名字空间
- this 用于在类内部表示当前实例对象
- owner 用于成员函数中表示调用函数的主体对象
- global 用于表示全局名字空间
- self 用于表示当前名字空间

通过对象的下�?`[]`、直接下�?`[[]]`、成员操作符 `.` 指定的成员名字不会被解析为语法关键字，例�?

```aardio aardio
io.namespace = "io"
io["namespace"] = "io"

```

上面�?`.namespace` �?\["namespace"\] 都不会被解析为语法关键字�?
另外 aardio 中的部分内核提供的保留函数在编辑器中也默认显示为蓝色。请参考： [保留函数](builtin-function/index.html)

## 分隔�?
aardio 使用半角空格、制表符、回车换行、分号等作为分隔符，不允许使用全角空�? `'\u3000'`)或HTML空格( `'\u00A0'`)作为语法分隔符。在 HTML 模板语法中，还可以使�?`<? ?>` 作为代码分隔符�?
## 注释

注释是被标明不是程序代码、在运行时跳过不执行的附加说明内容�?
### 1\. 行注�?
单行注释�?`//` 开始，到行尾结�?

### 2\. 块注�?
块注释以 `/*` 开始，�?`*/` 结束，首尾的 `*` 字符可以有一或多个，�?`*` 字符的数目必须首尾匹配�?
块注释可以包含换行，可用于包含多行注释�?
## 操作�?operand)

操作数表示由操作符操作的数据。操作数可以是常量、变量、字面量、函数返回值�?
## 操作�?operator)

操作符（运算符）指代码中对操作数进行特定操作或运算的标点符号(不允许使用全角标点、在 aardio 编辑器中全角标点、全角空格将以红色纠错背景显�?�?
关于操作符请参考下面的链接�?
- [成员操作符](operator/member-access.html)

- [调用操作符](function/definitions.html#call)

- [算术运算符](operator/arithmetic.html)

- [按位运算符](operator/bitwise.html)

- [等式运算符](operator/equality.html)

- [逻辑运算符](operator/logical.html)

- [关系运算符](operator/comparison.html)

- [连接运算符](operator/concat.html)

- [取长运算符](operator/len.html)

- [优先级](operator/precedence.html)

- [运算符重载](operator/overloading.html)


注意�?
> 字面量以及定义执行代码的对象（函数定义、类定义、lambda 表达式）不能直接在右侧写一元操作符（成员操作符、调用操作符），除非在外面加一层括号将其转换为普通表达式，例�?`( function(){} )()` �?
## 字面量（literal�?[\#](\#literal)

字面量指的是在源代码中直接表示值的标记（notation）�?
aardio 中字面量有：

- 数值，例如 `123` �?- 以字面值表示的字符串：

  - 以双引号、反引号包含�?[原始字符串](datatype/string.html#raw) �?  - 以单引号包含�?[转义字符串](datatype/string.html#escaped)�?  - 在赋值语句中用注释作为右值表示的 [注释字符串](datatype/string.html#comment)�?- 布尔�?`true`, `false` �?- 空�?`null` �?- 直接�?`{}` 构造的表（或数组）�?
字面量后面不能直接写 [成员操作符](operator/member-access.html)，例�?`{}.name` 有语法错误，将字面量放在括号内写�?`（{}�?name` 才不会报语法错误�?
## 表达�?expression)

表达式用于计算或返回数据值�?
- 单个操作数可以构成一个表达式�?
- 操作数、运算符可以组成表达式，使用运算符对操作数进行运算并返回一个新的值�?
- 一个表达式可以作为另一个表达式的操作数�?
- 函数返回值可以作为表达式�?
- 匿名函数、匿名类定义、lambda 函数都可以作为表达式�?
除了函数调用语句的返回值是表达式，其他独立执行的语句不能作为表达式使用，例如：

- 赋值语句不能作为表达式�?
- 自增自减语句不能作为表达式�?- 具名函数、具名类定义不能作为表达式，只能作为独立语句运行�?
## 语句(statement) [\#](\#statement)

我们编写的程序由语句组成�?
程序中的最小指令单元称为语句�?
基本语句由关键字、操作数、操作符、表达式等组成�?
包含多个语句、或语句块的语句称为复合语句�?
一个基本语句是由尾部的分号表示结束的逻辑行，

如果能保持语句在语义上的独立完整性，分号�?”通常可以省略�?
语句块由一对大括号 `{}` 界定，语句块可以包含多个基本语句或者复合语句�?
�?aardio 里允许用 `begin end` 替代 `{}` 包含语句块，�?aardio 建议大家使用简洁且风格一致的 `{}` 包含语句块，尽量减少或者避免使�?`begin end` 替代 `{}` 的写�?。aardio 支持这个语法的初衷是希望对于嵌套过深的语句块可以用不同的语句块标记让代码的结构更清晰，但实际上编码中本就应当尽量避免嵌套过深的语句块�?
1. 基本语句:

   [赋值语句](statements/assignment.html)

   [函数调用语句](function/definitions.html#call)

   [import语句](../library-guide/import.html)

2. 语句�?
   [语句块](statements/blocks.html)

3. 控制语句

   [条件判断语句](statements/branching.html)

   [循环语句](statements/looping.html)

   [容错语句](statements/try.html)

4. 定义语句

   [定义名字空间](namespace.html)

   [定义函数](function/definitions.html)

   [定义类](class/class.html)


## 语句与表达式的概念区�?[\#](\#stat-vs-exp)

aardio 语言严格区分表达式、语句的概念�?
表达式用于表示数据的值，而语句用于表示独立执行的代码。我们可以用分号分隔独立语句，但不能用分号分隔独立表达式�?
�?aardio 中除了函数调用可以是一个独立语句而函数的返回值可作为表达式使用，其他语句与表达式必须严格区分不能相互替代�?
正确用法与错误用法示例：

- `1+1; //错误，单独的表达式不能作为语句`![](../icon/error.gif)

- `var num = 1+1: //正确，表达式组成语句`![](../icon/ok.gif)

- `console.log( num ); //正确，函数调用构成独立语句`![](../icon/ok.gif)

- `console.log; //错误，表达式（函数对象）不能作为语句`![](../icon/error.gif)

- `var func = console.log: //正确，函数对象可以作为操作数构成表达式`![](../icon/ok.gif)

- `var tfunc = type( func ); //正确，函数返回值是一个表达式`![](../icon/ok.gif)

- `num++; //正确，自增赋值构成独立语句`![](../icon/ok.gif)

- `num = num++;//错误，自增语句不能作为表达式`![](../icon/error.gif)


要点�?
1. 表达式可以包含在括号�?
   您可以像下面这样�?

   `num = ( (1+1)+2 )`

   所有表达式都可以放在括号里�?
   但是下面这样就不对了�?
   `( print(123) ) //出错了`![](../icon/error.gif)

   语句不能包含在括号里�?
2. 独立语句可以用分号分隔�?
   你可以像下面这样�?


   ```aardio aardio
   num = ( (1+1)+2 );

   ```


   赋值语句是一个语句，可以在独立语句后面添加分隔符�?
   但是普通表达式不能用分号分隔（表达式刚好位于独立语句结尾不算）�?
   例如下面这样就不对了�?
   `num = ( (1+1); +2 ) //普通表达式不能用分号分隔`![](../icon/error.gif)


   > 注意：可以在 for 循环里用分号分隔计数条件，在表或类构造器里可以用分号分隔元素�?

[Markdown 格式](https://www.aardio.com/zh-cn/doc/language-reference/basic-syntax.md)

