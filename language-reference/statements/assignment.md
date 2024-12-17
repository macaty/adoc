[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# 赋值语�?
## 一、普通赋值语�?
赋值语句改变一个变量的值�?
赋值语句不能作为表达式使用，也不能作为表达式的一部分使用�?
赋值语句必须是独立的语句，普通的赋值语句（在循环语句中初始化循环变量除外）不能作为其他语句的一部分，例�?`v = v2 = 100` 的写法是错误的�?
### 赋�?
示例:

```aardio aardio
a = 120;

```

赋值基本规则：

- 如果将一个变量赋值为 null 等同删除这个变量�?- table,cdata,function 类型的数据在赋值时并不会创建新的值而只是添加一个引�?即新变量仍然指向同一个对�?�?- 将数据作为函数的参数时也会进行赋值操作，作为参数 table,cdata,function 同样是按引用传递的�?- 相同字符串（ string 类型 ）也会引用同一块内存，但修改字符串时总是会创建新的对象，所以改动一个字符串不会影响另一个字符串�?
### 多重赋�?
示例:

```aardio aardio
a,b,c = 1,2,3;

```

以上的写法等效于�?
```aardio aardio
a=1;
b=2;
c=3;

```

多重赋值时，右边的操作数如果多于左边的变量数目则丢弃多余的，右边的操作数不足则返回 null 值�?
示例:

```aardio aardio
a,b,c = 0;

```

上面的代码执行后 a 等于 0 , �?b,c　的值都�?null�?
如果一个函数有多个返回值时，也可以使用多重赋值的方法，例如：

示例:

```aardio aardio
var a,b,c = table.unpack( { 1 ; 2 ; 3 } )

```

### 使用 var 语句定义局部变�?[\#](\#var)

使用局部变量有两个好处:

1. 避免命名冲突
2. 访问局部变量的速度比访问全局变量（或当前名字空间变量）快�?
请参考：

- [局部变量](../variables-and-constants.html#var)
- [函数局部变量](../function/definitions.html#var)

局部变量需要用 var 语句声明�?
示例:

```aardio aardio
import console;

//声明一个局部变�?str
var str = "123";

//语句块开�?{
    //局部变量为块级作用域，仅在语句块内部有�?    var str = "hello" /

    //局部变量的值是可以改变�?    str = "Hello, World!"

    //显示 "Hello, World!"
    console.log(str);
}
//语句块结�?
console.log(str); //显示123

```

如果 var 后面使用一对括号，则圆括号内部可以写多�?var 语句并省略前面的 var 关键字，示例�?
```aardio aardio
var (
    a = 123;
    b = 456
);

```

### 使用赋值语句定义变量、常�?
没有�?var 语句声明过的标识符默认为当前名字空间的常量或变量�?
一个从未赋值的常量或变量默认值为 null�?
当前名字空间的成员名称如果首字符为下划线，并且长度大�?1 个字节并小于 256 个字节，则是一个命名常量，否则为变量�?
参�? [变量与常量](../variables-and-constants.html)

名字空间只包含大写字母与下划线的命名常量�?[全局常量](../variables-and-constants.html#global-constant)，全局常量在所有名字空间都可以直接使用，不需要再添加表示全局名字空间�?`..` 前缀�?
示例�?
```aardio aardio
//将变量声明为当前名字空间下的成员变量
value = 100;

//以下划线开始的成员常量，赋为非 null 值以后就不能再更改值�?_value = 100;

//以下划线开始的全局常量，赋为非 null 值以后就不能再更改值�?_VALUE = 100;

//使用::操作符定义的全局常量，只能赋值一�?::Value = 100;

```

### 使用赋值语句删除变�?
将一个变量赋值为 null，删除这个变量。例如：

```aardio aardio
value = null;

```

## 二、复合赋值语�?
`a = a + b` 可以写成 `a += b`�?
所有二元操作符都可以按上述规则书写�?
例如�?
```aardio aardio
a -= b;
a *= b;

```

复合赋值操作符不能包含空格，如 `a + = b;` 是错误的 ![](../../icon/error.gif)，正确的应当�?`a += b;`![](../../icon/ok.gif)

复合赋值的几个特例�?
- 初始化赋�?
  初始化赋值使用复合赋值语句： `A := c` �?
  `A := c` 等价�?`A = A:c` 。如�?`A` �?null 空值，则将 `c` 赋值给 `A`�?
  定义命名常量时，为避免重复赋值，通常使用会初始化赋值语句�?
  参�? [命名常量](../variables-and-constants.html#named-constants)

- 条件赋�?
  示例�?
  `str ?= string.lower(str)`

  上面的复合赋值语句等价于�?
  `str = str and string.lower(str)`

  如果 str 不为 null 空值，则执行后面的赋值语句�?
  其语义如下：


  ```aardio aardio
  if(str != null){
    str = string.lower(str)
  }

  ```


  这样可以避免 str 为null 空值时，string.lower 抛出错误。如�?str 为空，则等号右侧的语句根本不会执行�?

## 五、自增自减赋�?
自增语句 `a++` 等价�?`a += 1`�?
自减语句 `a--` 等价�?`a -= 1`�?
要特别注意在 aardio 中语句不是表达式，自增自减语句同样也必须是独立语句不能作为表达式使用�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/language-reference/statements/assignment.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/language-reference/statements/assignment.md')

