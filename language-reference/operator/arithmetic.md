[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# 算术运算�?
算术运算符对两个操作数进行算术运算�?
如果参考算术运算的其中一个操作数是字符串则尝试转换为数值运算，转换失败则抛出异常。字符串在自动转换为数值时，忽略首尾空白字符，空白字符串会转换�?0，自动转换数据类型时不会调用 `_tonumber` 元方法。请参�? [隐式数据类型转换](../variables-and-constants.html#type-coercion)

如果参考算术运算的操作数是数值、字符串以外的其他数据类型则查找该对象的元方法进行运算，如果对象并未定义元方法则抛出异常�?请参考： [重载操作符](overloading.html) [元方法](../datatype/table/meta.html)

算术运算符列表：

运算符说明`+`加`-`�?二元运算�?、取�?单目运算�?`*`乘`/`除`%`模`**`乘方

![](../../icon/info.gif) 要特别注�?`+` 运算符的规则�?[#](#add)

- 如果一个操作数是数值，而另一个操作数是字符串，则尝试将字符串转换为数值做算术相加运算，转换失败则报错�?- 如果两个操作数都是字符串，则尝试将两个操作数都转换为数值做算术相加运算，转换失败则改为字符串连接操作。不应依赖此规则做字符串连接，明确写�?`++` 可以避免不必要的转换，也可避免不必要的误操作�?- 引号（双引号、单引号、反引号）前后的 `+` 运算符将自动转换为字符串 [连接运算�?++](concat.html)

aardio 中的数值默认存储为 64 位浮点数（即原生类型中的 double 类型）。参�?[数据类型 \- number](../variables-and-constants.html#number)

�?aardio 中算术运算结果是 64 位浮点数（double），所以可能出现小数。我们可以使�?math.round 函数对计算结果四舍五入取整，也可以使�?math.floor 函数向下取整，或使用 math.ceil 函数向上取整。参考： [math 库函数](../../library-guide/builtin/math.html)

以整除为例，将用 `/` 运算符计算除法的结果转换为整数的 aardio 示例如下�?
```aardio aardio
import console;

//整除
var num = math.round( 10 / 3 );

//在控制台显示计算结果
console.log("计算结果�? ,num);

console.pause(true);

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/language-reference/operator/arithmetic.md)

