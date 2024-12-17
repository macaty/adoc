[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# 按位运算�?
aardio 的所有按位运算符总是将操作数转换�?32 位整�?�?`>>>` 转为无符�?32 位整数以外，其他位运算符转为 32 位有符号整数)，然后以二进制形式按位运算�?
逻辑按位运算�?0 为假�? 为真�?
按位运算符不支持运算符重载�?
aardio 支持自定义进制数值，语法为　`自定义进�?+ '#' + 数值`�?因此可以�?`2#101` 表示二进制数 `101`，按位运算符都是针对二进制数的操作，因此下面使用二进制数来演示。在实际使用时可以使用十进制数�?所有进制最终都是以二进制存储、按位运算并无区�? �?
## 按位�? `&` [\#](\#and)

按位与运算符"&"是双目运算符。其功能是对参与运算的两数各对应的二进制位做按位与运算。只有对应的两个二进制位均为 1 时，结果位才�? ，否则为 0。参与运算的数以补码方式出现�?
示例�?
```aardio aardio
import console.int;

//按位�?var b = 2#101 & 2#100 ;

//显示2#100
console.printf("2#%b",b);

```

## 按位�? `|` [\#](\#or)

按位或运算符 `|` 是双目运算符。其功能是参与运算的两数各对应的二进制位做按位或运算。只要对应的二个二进制位有一个为1时，结果位就�?。参与运算的两个数均以补码出现�?
示例�?
```aardio aardio
import console.int;

//按位�?var b = 2#101 | 2#110 ;

//显示2#111
console.printf("2#%b",b);

```

## 按位异或: `^` [\#](\#xor)

按位异或运算�?`^` 是双目运算符。其功能是参与运算的两数各对应的二进制位做按位异或运算。只要对应的二个二进制位相同，结果位就为 0 ,否则�?1。参与运算的两个数均以补码出现�?
示例�?
```aardio aardio
import console.int;

//按位异或
var b = 2#101 ^ 2#110;

////显示2#011
console.printf("2#%b",b);

```

## 按位取反: `~` [\#](\#not)

按位取反运算�?`~` 为单目运算符，具有右结合性。其功能是对参与运算的数的所有二进制位做按位取反运算�?
例如:

```aardio aardio
import console.int;

//按位取反
var b = ~2#101;

//显示 2#11111111111111111111111111111010
console.printf("2#%b",b);

```

## 按位左移: `<<` [\#](\#left-shift)

`a << n` 将数�?a 按位向左移动 n �?如果 n 大于等于 32，则�?n�?32 取模结果的位�?)。左�?n 位就相当于乘�?2 �?n 次方(在没有溢出的前提�? �?
示例�?
```aardio aardio
import console.int;

//按位左移
var b = 2#101 << 1;

//显示2#1010
console.printf("2#%b",b);

```

## 按位右移: `>>` [\#](\#right-shift)

`a >> n` 将数�?a 按位向右移动 n �?如果 n 大于等于 32，则�?n �?32 取模结果的位�? ，保留符号位(负数保持最高位�?1 ) 。右�?n 位就相当于除�?2 �?n 次方(在没有溢出的前提�?

示例�?
```aardio aardio
import console.int;

//按位右移
var b = 2#101 >>1;

//显示2#10
console.printf("2#%b",b);

```

## 按位无符号右�? `>>>` [\#](\#unsigned-right-shift)

> a >>> n 将数值a按位向右移动n�?如果n大于等于32，则为n�?2取模结果的位�? ，不保留符号�?负数不保持最高位�?，因此右移后会变成正�?�?
示例�?
```aardio aardio
import console.int;

//按位无符号右�?var b = -2>>>18;

//显示 16383
console.print(b);

```

可以通过右移 0 位将有符号数强制转换为无符号数�?
例如 `-1 >>> 0` 的值为 0xFFFFFFFF —�?其作用等价于 `raw.convert( {int value = -1},{INT value}).value`�?
[不声明调用原�?API](../../library-guide/builtin/raw/directCall.html) 默认会返�?32 位有符号整数，如果原 API 返回的是 32 位无符号整数，那么只要简单的将返回�?`>>> 0` 就可以得到原来的无符号数值了�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/language-reference/operator/bitwise.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/language-reference/operator/bitwise.md')

