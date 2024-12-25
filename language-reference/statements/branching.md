[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# 判断语句

参考：

- [等式运算符](../operator/equality.html)
- [逻辑运算符](../operator/logical.html)
- [关系运算符](../operator/comparison.html)
- [布尔值](../datatype/datatype.html#boolean)
- [隐式数据类型转换](../datatype/datatype.html#type-coercion)

## if 语句

if 语句包含条件判断部分、执行代码部分�?
执行代码部分可以是一句代码（不能是单个分号表示的空语句），或者一�?[语句块](blocks.html)�?
�?if 语句将条件表达式返回的结果与布尔�?true 进行比较，比较使�?[等式运算符](../operator/equality.html)( 支持自动类型转换�?`_eq` 元方�?)�?
if 语句可选包含任意多�?elseif 分支判断语句，可选在最后包含一�?else 语句�?
if 语句可以嵌套使用�?
一个标准的 if 语句示例:

```aardio aardio
import console;

var a=1;

if(b==1){
    if(a==1)  {
        console.log("if");
    }
}
elseif(a==11){
    console.log("elseif");
}
else{
    console.log("else");
}

console.pause();

```

> 注意：上面的 `elseif` 如果改为 `else if` 相当于在 `else` 语句嵌套了一个新�?if 语句，这通常是不必要的�?
## select case 语句

select 指定一个选择器变量或表达式，case语句列举不同的值或条件值，第一个符合条件的 case 语句将会执行（执行第一个符合条件的 case 语句以后退�?select 语句，不会连续执行多�?case 语句）�?
![](../../icon/info.gif) case 语句默认调用 [恒等式运算符](../operator/equality.html) 进行比较。也可以自行指定操作符�?
例如�?
```aardio aardio
import console;

var a = 0;

select( a ) {

    case 1 { //判断 1===a 是否为真
        console.log("a==1")
        //其他代码
    }
    case 1,9,10 {  //判断 a　是否其中的一�?        console.log("a�?,9,10其中之一")
    }
    case 10;20 { //判断 ( 10<=a and a <=20 ) 是否为真
        console.log("a�?0�?0的范�?)
    }
    case !=0{ //判断 a是否不等�?，这是自已指定关系运算符的示�?        console.log("a不等�?")
    }
    else{ //所有条件不符时执行else语句�?        console.log("a是其他�?0)")
    }
}

```

select case 语句也可以嵌套使用，�?select case 语句嵌套写的可读性不是很好，一般应当避免�?
[Markdown 格式](https://www.aardio.com/zh-cn/doc/language-reference/statements/branching.md)

