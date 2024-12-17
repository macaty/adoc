[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# System.Numerics 库模块帮助文�?
## System.Numerics 成员列表

.NET 数值扩展类型名字空�?System.Numerics�?
.NET 4.0 开始支持。Win10 开始自�?.NET 4.6 �?
### System.Numerics.?

.NET 名字空间、类、结构体的成员，

可访问成员名字空间、类、枚举、静态属性或字段�?
导入的类可用于构�?.NET 对象，传�?.NET 则自动转为该类的 Type 对象

[返回对象:dotNetNameSpaceObject](../dotNet/appDomain.html#dotNetNameSpaceObject)

### System.Numerics.BigInteger()

创建大整数�?
参数 @1 指定字符串时调用 TryParse 函数创建对象，失败返�?null�?
否则调用 System.Numerics.BigInteger 构造函数，

非字符串参数用法参�?.NET 文档�?
参数 @1 如果�?0x前缀的字符串，则�?6进制解析为数值�?
16进制字符串首个数字为0则总是解析为正数，

否则开始的数值大�?x80时生成负数�?
[返回对象:sysNumericsBigIntgerObject](#sysNumericsBigIntgerObject)

### System.Numerics.Complex()

[返回对象:sysNumericsComplexObject](#sysNumericsComplexObject)

### System.Numerics.Complex(实部,虚部)

创建复数�?
支持常用运算符，参与运算的数必须也是 System.Numerics.Complex �?
支持�?tostring 函数转换�?aardio 字符串�?
### System.Numerics.assembly

导入�?.NET 名字空间的程序集对象�?
[返回对象:dotNetCrlAssemblyObject](#dotNetCrlAssemblyObject)

## System.Numerics.BigInteger 成员列表

支持任意大整数的数值类型�?
没有下限或上限，可以包含任何整数的值�?
支持常用运算符，参与运算的数必须也是 System.Numerics.BigInteger �?
支持�?tostring 函数转换�?aardio 字符串�?
tostring �?2 个参数为 "x"�?X"时返�?16 进制字符串�?
大数运算也可以使�?math.bignum 扩展库�?
### System.Numerics.BigInteger.Parse()

参数 @1 指定字符串�?
解析字符串中的整数值�?
参数 @1 指定字符串�?
解析字符串中的整数值�?
### System.Numerics.BigInteger.TryParse()

参数 @1 指定字符串�?
解析字符串中的整数值，失败返回 null

## System.Numerics.Complex 成员列表

复数�?
可参考：math.complex 扩展库�?
### System.Numerics.Complex.?

更多复数函数用法请参�?.NET 文档

## sysNumericsBigIntgerObject 成员列表

### sysNumericsBigIntgerObject.?

此对象的其他可用函数请参�?.NET 文档

### sysNumericsBigIntgerObject.ToString("X")

转换�?16 进制字符�?
### sysNumericsBigIntgerObject.ToString()

转换为字符串

### sysNumericsBigIntgerObject.byRef(true)

传参方式设为传址（用于引用或输出参数�?
## sysNumericsComplex 成员列表

### sysNumericsComplex.?

此对象的其他可用函数请参�?.NET 文档

### sysNumericsComplex.Imaginary

获取虚部�?
### sysNumericsComplex.Magnitude

获取复数的量值（或绝对值）�?
### sysNumericsComplex.Phase

获取复数的相位�?
### sysNumericsComplex.Real

获取实部�?
### sysNumericsComplex.ToString()

转换为字符串�?
参数可用字符串指�?.NET 字符串标准或自定义格式化串�?
用法请参�?.NET 文档�?
### sysNumericsComplex.byRef(true)

传参方式设为传址（用于引用或输出参数�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/System/Numerics.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/System/Numerics.md')

