[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# builtin.math 库模块帮助文�?
## math 成员列表

### math.e

自然对数的底数，约等�?2.718281828459 �?
### math.isFinite()

如果参数是一个有效数�?

并且不是正负无穷大则返回 true，否则返�?false�?
如果传入字符串会直接返回 false

### math.isInteger()

参数是一个数值并且是整数返回true，否则返回false�?
如果传入字符串会直接返回 false

### math.isSize64()

判断参数是否 math.size64 长整数对�?
### math.mulDiv(a,b,c)

返回a乘b再除以c的结�?并自动四舍五入转为整�?
可尽量使运算不会溢出,运算错误则返�?1

注意这个函数是系�?API 函数�?
参数只能传入数值不能传入字符串

### math.round

四舍五入，舍入规则以取整为例�?
小数小于0.5取相邻的绝对值更小的整数�?
小数大于0.5取相邻的绝对值更大的整数�?
小数等于0.5取相邻的正无穷大方向的整数�?
注意四舍五入非常多的规则�?
各种语言的默认实现并不完全一致，

计算机浮点数都存在可容忍的精度误�?
### math.round(数�?精度)

四舍五入取接近的数，

精度指定小数后的位数,默认�?（取整）

### math.roundToEven

aardio 改良版银行家舍入法，

舍入规则为：尾数四舍六入，五后为零前凑偶（只看一位零）�?
解决问题1:1�?出现机率一样，5�?进位导致进多舍少�?
解决问题2:浮点数误差导致的不合理舍入�?
注意四舍五入非常多的规则�?
各种语言的默认实现并不完全一致，

计算机浮点数都存在可容忍的精度误�?
### math.roundToEven(数�?精度)

使用改良版银行家舍入法转换并返回参数@1指定的数值，

参数@2指定返回数值的小数位数,默认�?（也就是取整�?
### math.stringify(数�?最大精�?

数值或 math.size64 对象转换�?0进制字符�?最大精度默认为15,

不使用科学计数法，小数尾部不会有0

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/builtin/math.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/builtin/math.md')
