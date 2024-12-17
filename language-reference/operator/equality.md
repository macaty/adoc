[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# 等式运算�?
等式运算符比较两个操作数是否相等，并返回 boolean 类型的�?true �?false)�?
## 一、全等式运算�?
全等式又称为恒等式，要求数据类型绝对相等、并且不会调�?`_eq` 元方法。因此也不能重载恒等操作符�?
运算符说明`===`恒等运算符`!==`非恒等运算符

如果是数字，字符串，指针，布尔值，在值与类型都相等时恒等式返回真，返则返回假�?
如果是其他传址对象，指向同一个对象返回真，否则返回假�?
示例结果`"abc" === "abc"`true`null === false`false

## 二、等式运算符

等式运算符判断两个操作数是否相等�?
运算符说明`==`等式运算符`!=`不等式运算符`=`在表达式中可以替�?=

"等式"�?恒等�?最大的不同�?等式"允许类型自动转换。与逻辑值有关的类型自动转换规则�?
1. 在逻辑运算中，�?0\. �?null、非 false �?true，反之为 false�?
2. 使用 [等式运算符](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/language-reference/operator/..operatorequality.html  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ������������ļ�δ�ҵ���  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/language-reference/operator/..operatorequality.html') 比较 2 个值时�?

   - 任意值与 true,false 比较则先转换为布尔值�?
   - 非布尔值与数值比较，则先转换为数值，然后比较数值是否相等�?
     例如 `null == 0` 就属于非布尔值与数值比较，�?null 转换为数值还�?null，null �?0 不是相等的数值。所�?`null == 0` 会返�?false �?
     再例�?`""== 0` �?`' \t\r\n'== 0` 同样属于非布尔值与数值比较，空白字符串自动转换为数值时返回 0，所�?`""== 0` �?`' \t\r\n'== 0` 都会返回 true�?

> 注意：\*\*当等式或不等式的操作数中只有数值而没有出现布尔值，就不应当错误地根据布尔值转换规则去推导结果。\*\*

请参考： [隐式类型转换](../datatype/datatype.html#type-coercion)

### 1\. 操作数的数据类型相同之间的等式比较规�?
对于数�? type.number )、字符串( type.string )、指�? type.pointer )，布尔�? type.boolean )等传值类型比较值是否相等�?
示例结果`"abc" == "abc"`true`123 != 456`true

对于 table、cdata、bufffer 等传引用类型，当引用同一个对象时相等。否则检查参考比较的两对象是否存在相同的 `_eq` [元方法](../datatype/table/meta.html) ，如果存在就调用 `_eq` 元方法判断是否相等。如果操作数不是同一个对象且没有相同�?`_eq` 元方法则不相等�?
示例结果说明`::User32 != ::Kernel32`true引用了不同的对象`{} == {}`false引用了不同的对象`raw.buffer("abc")==raw.buffer("abc")`false引用了不同的对象`time.now() == time.now()`true调用time.now().\_eq元方法比�?
### 2\. 非布尔值与布尔值之间的等式比较规则

0, null �?false 相等，而所有非零、非 false、非 null 值与 true 相等�?
表达式结果`0==false`true`null==false`true`1==false`false`if( 1 ) console.log("true")`条件符合，执行代�?console.log("true")

### 3\. 非布尔非数字值与数字值之间的等式比较规则

非布尔非数字值与数值比较，则先转换为数值，然后比较数值是否相等�?要注意字符串在自动转换为数值时，空白字符串会转换为 0，转换忽�?`_tonumber` 元主法�?
表达式结果`"123"==123`true`"abc"==123`false`""==0`true`'\r\n\t '==0`true`null==0`false

### 4\. 其他不同类型的操作数之间的等式比较规�?
如果数据类型不同、会尝试进行类型转换后进行比较。如果类型转换失败、也无适合�?\_eq 元方法可以调用则返回 false�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/language-reference/operator/equality.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/language-reference/operator/equality.md')

