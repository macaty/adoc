[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# 元表

使用元表可以自定义对象的默认行为、操作符�?
## 什么是元表

一个对象可以用另一�?table 对象(元表)来定义一些元方法(metamethods)。用来定义元方法的表称为元表(metatable)。元�?metatable)允许我们改变对象的行为�?
元表(metatable)中的函数称为元方法，通常用来重定义运算符�?例如对两个表(table)进行相加时，它会检查两个表是否有一个表有元�?metatable)，并且检查元�?metatable)是否�?`_add` 函数。如果找到则调用这个 `_add` 函数去计算结果�?
虽然理论上所有对象都可以指定元表，但一般这样做是无意义的�?
元表主要应用�?table 对象�?
## 设置与获取元�?
在表构造器中使�?`@` 操作符就可以�?`@` 操作符后面的表对象指定为元表�?
示例�?
```aardio aardio
//定义一个元�?_metaTable = {
    //添加元方�?    _get = function(k) {

        owner[[k]] = k + " 通过元方法创建的�?
        return owner[[k]] //不调用元方法
    };
}

var tab = {

    //使用 @ 操作符设置元�?    @_metaTable
}

```

也可以在 `@` 操作符后面用字面量直接构造元表�?
示例如下�?
```aardio aardio
var tab = {
    //使用 @ 操作符设置元�?    @{
        //添加元方�?        _get = function(k) {

            owner[[k]] = k + " 通过元方法创建的�?
            return owner[[k]] //不调用元方法
        };
    }
}

```

在表对象后面加上 `@` 操作符可以获取或设置元表�?
示例�?
```aardio aardio
//设置元表
tab@ = {};

//获取元表
var meta = tab@;

//获取元方�?var f = tab@._get;

```

元表中的字段通常会使用下划线 `_` 作为首字符以声明�?[只读成员](_.html#readonly-member) 以禁止随意改动对象的行为�?
元表中的方法我们称之�?元方�?，元表中的属性我们称之为"元属�?，但很多时候同名的"元方�?�?元属�?可以相互替代，一�?元属�?允许定义函数并自动获取返回值，而一�?元方�?也允许直接指定一个固定的值而不是定义一个函数，所�?aardio 并不严格区分这两个术语�?
## 锁定元表 [\#](\#float)

对象指定元表以后，默认会锁定该元表，不能移除锁定的元表，也不能用其他的元表替换锁定元表�?
只有在元表中�?`_float` 属性指定为 true 时，元表就不会锁定并且可以随时被移除或替换。也就是说只有元表自己才能决定它自己是不是可以被移除替换�?
示例�?
```aardio aardio
//创建非锁定的元表
tab@ = { _float = true };

//替换元表成功
tab@ = {};

//不能替换默认锁定的元�?tab@ = {};

```

## 元方�?元属性列�?[\#](\#meta-methods)

请参考： [运算符、表达式 \- 运算符重载](../../operator/overloading.html)

元表中的属性、方法列表：

元属�?元方法说明`_weak`弱引用不会增加引用计数、不会阻止垃圾回收器删除对象�?
赋值为 "kv" 表示弱引用键、值�?
赋值为 "v"　表示弱引用值�?
赋值为 "k" 表示弱引用键。`_type`自定义类�?如果值为"object",指明该对象为JSON兼容的对象，如果值为"array",指明该对象为JSON的数组。`_readonly`如果显式指定此元属性为 false，则该表可以重写属性名首字符为下划线的字段( 禁用只读成员保护 )�?
`_readonly` 的值只能为 false �?null 。设�?`_readonly` 为任何非null值都会被强制转换�?false, 只有不指定此属性的�?即保�?null �?才能启用只读成员保护（所有名字以下划线开头的属性禁止修改非null值）�?
 global对象无论元属�?`_readonly` 怎么设置都会被忽略，只读成员保护总是启用状态�?[#](#_readonly) [关于表的只读成员](_.html#readonly-member)`_defined`用于返回对象的预定义已排序键名，被用于table.eachName等函数。`_keys`可用于table.keys等函数动态获取对象的键名列表（例如动态生成键值对的外部JS对象可使用这个元方法返回成员名字列表）。`_startIndex`用于table.eachIndex等函数动态指定数组的开始下标。`_get = function(k,ownerCall) {<br> <br> }`成员（属性）操作�?`.`

索引（下标）操作�?`[]`

如果�?[属性（.）操作符或下标操作符（\[\]）](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/language-reference/operator/member-access.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/language-reference/operator/member-access.md') 读取表中不存在的键会触发 `_get` 元方法并返回值�?
注意：使�?`owner[[member]]` 形式的直接下标以�?namespace 语句打开新的名字空间不会触发元方法。with 语句打开新的名字空间则会触发元方法。在 aardio �?NET 名字空间 依赖元方法自动导入下级名字空间的 ，所�?namespace 只能用于打开已导入的 .NET 名空字间（否则应改用 with 语句）�?
`_get` 不但可以是一个函�?也可以指定一�?table 对象(找不到成员就�?`_get` 指定�?table 里找)�?
如果�?`_get` 元方法是一个函数，则调用参�?k 为键名�?
使用 `owner[member]` 形式的下标操作符触发 owner 对象�?`_get` 元方法时 ownerCall 参数的值为 null �?
使用 owner.method() 形式的成员函数触�?owner 对象�?`_get` 元方法时 ownerCall 参数的值为 true 。ownerCall 参数如果�?true 则应当返回一个函数对象�?
其他方式访问表的成员触发对象�?`_get` 元方法时 ownerCall 参数的值为 false�?
`_set = function(k,v,ownerAttr) { }`成员（属性）操作�?`.`

 索引（下标）操作�?`[]`

 如果�?[. �?\[\] 操作符](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/language-reference/operator/member-access.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/language-reference/operator/member-access.md') 给表中不存在的键赋值会触发 `_set` 元方法�?
 注意：使�?`owner[[member]]` 形式的直接下标赋值不会触发元方法�?
`_set` 元方法的 k 参数为新的键，v 参数为新的�?�?
 在赋值语句中使用 `owner[member] = value` 形式的下标操作符赋值触�?owner 对象�?`_set` 元方法时 ownerAttr 参数的值为 false，其他任何方式触发对象的 `_set` 元方法时 ownerAttr 参数的值为 true �?
 使用形如 `{ ["key"] = value}` 的格式在表内使用下标定义键名时如果触�?`_set` 元方�?ownerAttr 的值仍然为 true�?
 只有 `owner[member] = value` 的形�?ownerAttr 参数才会�?false，也就是说下标操作符前面必须有一�?owner 对象。`_tostring = function(...) { }`除布尔值、字符串 以外的对象作为参�?@1 调用 tostring 函数可触发该对象�?`_tostring` 元方法，调用 tostring 的第二个参数开始的所有参数会作为 `_tostring` 的调用参数。`_tonumber = function() { }`除数值、指针、布尔值、字符串 以外的对象作为参�?@1 调用 tonumber() 会触发会调用该对象的 `_tonumber` 元方法转换为数�?。`_json`表对象可使用此元方法自定�?web.json.stringify() 处理该对象时返回的数据�?此元方法的回调参�?owner 为当前表对象。如果此元方法返回一个值则 web.json.stringify() 继续转换返回对象�?JSON�?如果此元方法的第二个返回值为 true，并且第一个返回值为字符串，�?web.json.stringify() 将第一个返回值直接放�?JSON 并不作任何转换。`_eq = function(b) { }`相等运算、不等运算符调用此元方法并取�?
 比较的两个对象必须指向相同的元方�?�?a@. `_eq` === b@. `_eq` ),否则默认规则进行比较.

`_le = function(b) { }`小于等于、大于等于运算符

 比较的两个对象必须指向相同的元方�?�?`a@._le === b@._le` )

 当调�?`a <= b` �? a 为元方法�?owner 对象(左参�?

当调�?`a >= b` �? b 为元方法�?owner 对象(右参数作为左参数)`_lt = function(b) { }`小于运算、大于运算符

 比较的两个对象必须指向相同的元方�?�?`a@._lt === b@._lt` )

 当调�?`a < b` �? a为元方法的owner对象(左参�?

 当调�?`a > b` �? b 为元方法�?owner 对象(右参数作为左参数)`_add = function(b) { }`加运算符

 调用元方法时,始终取左操作数作为元方法的owner参数.

 无论左操作数或右操作参数定义了此元方�?都可以触发自定义的运�?

 当左右操作数定义了不同的元方�?调用左操作数的元方法.`_sub = function(b) { }`减运算符

 调用元方法时,始终取左操作数作为元方法的owner参数.

无论左操作数或右操作参数定义了此元方�?都可以触发自定义的运�?

当左右操作数定义了不同的元方�?调用左操作数的元方法.`_mul = function(b) { }`乘运算符

 调用元方法时,始终取左操作数作为元方法的owner参数.

无论左操作数或右操作参数定义了此元方�?都可以触发自定义的运�?

当左右操作数定义了不同的元方�?调用左操作数的元方法.`_div = function(b) { }`除运算符

 调用元方法时,始终取左操作数作为元方法的owner参数.

无论左操作数或右操作参数定义了此元方�?都可以触发自定义的运�?

当左右操作数定义了不同的元方�?调用左操作数的元方法.`_lshift = function(b) { }`左移运算�?<<

 调用元方法时,始终取左操作数作为元方法的owner参数.

无论左操作数或右操作参数定义了此元方�?都可以触发自定义的运�?

当左右操作数定义了不同的元方�?调用左操作数的元方法.`_rshift = function(b) { }`右移运算�?>>

 调用元方法时,始终取左操作数作为元方法的owner参数.

无论左操作数或右操作参数定义了此元方�?都可以触发自定义的运�?

当左右操作数定义了不同的元方�?调用左操作数的元方法.`_mod = function(b) { }`模运算符

 调用元方法时,始终取左操作数作为元方法的owner参数.

无论左操作数或右操作参数定义了此元方�?都可以触发自定义的运�?

当左右操作数定义了不同的元方�?调用左操作数的元方法.`_pow = function(b) { }`幂运算符

 调用元方法时,始终取左操作数作为元方法�?owner 参数.

无论左操作数或右操作参数定义了此元方�?都可以触发自定义的运�?

当左右操作数定义了不同的元方�?调用左操作数的元方法.`_unm = function() { }`取负运算符，owner 参数为当前操作数`_len = function() { }`取长运算�?`#`。owner 参数为当前操作数。注�?table,string,null 这三种类型不能重载此操作符。`_concat = function(b) { }`连接运算�?
 调用元方法时,始终取左操作数作为元方法�?owner 参数.

无论左操作数或右操作参数定义了此元方�?都可以触发自定义的运�?

当左右操作数定义了不同的元方�?调用左操作数的元方法.`_call = function(...) { }`[函数调用](#_call)，owner 参数为当前操作数，其他参数为调用函数的参数�?
元方法还可以用于指定 COM 默认调用方法�?DISPID �? `DISPID_VALUE` �? `DISPID_VALUE` 调用会优先使�?`_call` 元方法执�?COM 默认调用，如果aardio 表对象、CDATA 对象未指�?`_call` 元方法， 则通过 `_item` 元方法获取默认调用表（以带参数方式读写该表属性）�?
 ActiveX 控件类的 COM 默认调用必须�?ODL 中指定，�?aardio.idl 中定义的 IDispatchExecutable 已指�?COM 默认调用属性为 Item�?
 例如�?
 VB �?VBA 写默认属�?`comObj("项目�?) = �?`

 读默认属性（或调用默认方法） `v = comObj("项目�?);`

aardio 中类似的是函数调用语法：

`comObj("项目�?)` �?`comObj("项目�?,"项目�?)`

aardio 使用函数读写默认值语法：

`comObj.setValue( value );`

`value = comObj.getValue();`

aardio 使用属性读写默认值语法：

`comObj.Value = value;`

`value = comObj.Value;`

aardio 使用属性读写带参数值语�?

`comObj.getItem("项目�?);`

`comObj.setItem("项目�?);`

这些写法主要用于操作 COM 函数，在原生 aardio 中并不常见。原�?aardio 代码用下标语法更方便�?
`_item`[\_item](#_item) 必须返回一个表对象，可直接指定一个表或返回表的函数�?
 aardio 表对象、cdata对象�?COM 接口中自动或调用 com.ImplInterface() 转换�?IDispatch 接口对象后支�?`_item` 元方法�?
`_item` 元方法用于在 COM 接口中返回支持枚举接口（ IEnumVARIANT ）的表对象�?如果未指定该元方法，�?IEnumVARIANT 接口默认枚举表对象自身�?
`_item` 元方法还可以用于指定 COM 默认调用表（COM 默认调用�?DISPID �? `DISPID_VALUE` �? `DISPID_VALUE` 调用会优先使�?`_call` 元方法执�?COM 默认调用，如果aardio 表对象、CDATA 对象未指�?`_call` 元方法， 则通过 `_item` 元方法获取默认调用表（以带参数方式读写该表属性）�?
 如果表对象未指定 `_item` 元方法，�?IEnumVARIANT 默认枚举表自身�?�?`DISPID_VALUE` 调用也会默认读写表自身�?
 com.activeX 创建�?ActiveX 控件类接口的规则略有不同�?ActiveX 控件类也只支�?`_enum` 指定 IEnumVARIANT 接口操作的枚举表�?�?ActiveX 控件类的 COM 默认调用必须�?ODL 中指定，�?aardio.idl 中定义的 IDispatchExecutable 已指�?COM 默认调用属性为 Item �?
 但通过 ActiveX 控件类接口返回的其他表对象、cdata 对象则仍然支持匿名的 COM 默认调用。`_toComObject`用于自定义一个表对象如何转换�?COM 对象，可定义为函数，也可以直接定义为对象。`_gc`用于触发析构函数。只能通过 table.gc �?gcdata 使用这个元方法�?
## 重载成员操作�?
重载所有操作符的写法基本都类似，下面我们以成员操作符为例演示并说明基本用法�?
如果访问表中不存在的属性会调用 `_get` 元方法，如果修改表中不存在的属性调�?`_set` 元方法�?
示例�?
```aardio aardio
import console;

//创建�?var tab = {};

//创建元表
tab@ = {

    //拦截获取成员的操�?    _get = function(k) {
        console.log(k+"被读�?)
        return k + "目前没有�?;
    }

    //拦截写入成员的操�?    _set = function (k,v) {
        console.log(k+"被修改值为"+v)
        owner[[k]]=v; //删除这句代码就创建了一个只读表
    }
};

//读取成员，显�?"x被读�?
var c = tab.x;

//写入成员，显�?"y被修改值为19"
tab.y = 19;

console.pause()

```

要点�?
- 在元方法中使�?owner 对象访问自身�?- �?`_get` 元方法中不需要再去重复读�?owner 对象的同名成员，因为只有读取不存在的成员时才会触�?`_get` 元方法。如果要拦截所有成员，那么更好的方法是用另一个表保存实际的数据。如果要改名读取自身的其他成员，要使用直接下标操作符 `[[]]` 以避免重复触�?`_get` 元方法，例如�?  `aardio
  tab@ = {
      _get = function(k) {
          if(type.isString(k)) {
              return owner[["real_" + k]];
          }
      }
  };
  `
- 同样只有写入本不存在的成员时才会触发 `_set` 元方法，如果要将新值写�?owner 对象自身，同样要使用直接下标操作�?`[[]]` 以避免重复触发元方法�?
参考：
[成员操作符、直接下标](../../operator/member-access.html)

aardio 里有一个在标准库中被大量使用的属性元表（util.metaProperty）主要就是基于上面的原理�?
参考：
[属性元表说明](../../class/class.html#metaProperty) [属性元表库参考](../../../library-reference/util/metaProperty.html)

## 代理�?[\#](\#proxy)

我们也可以用一个拥有元表的代理表接管对另一个真实对象的访问，以扩展、修改、封装真实源对象的方法与属性�?
这样做有几个好处�?
- 基于"组合优先于继�?的原则，用一个对象组合与封装其他的对象是非常方便的，可维护性也比较好�?- 如果真实的源对象已经指定了锁定的元表，我们在上面再封装一个代理表就可以使用元表接管对源对象的读写操作。一个典型的应用是对 COM 对象的封装，COM 对象本身就存在锁定的元表，如果我们需要用一个新的元表进一步封�?COM 对象，就需要创建一个代理表来封装原始的 COM 对象�?
示例�?
```aardio aardio
import console;

//为参�?@tab 指定的表创建一个代理表
function createProxy(tab) {

    //保存被代理的数据�?    var real = tab;

    /*
    创建一个代理表�?    你要访问真正的表（real）？
    先问过我（proxy）吧，我是他的经纪人！！�?    */
    var proxy = {};

    //创建元表
    proxy@ = {

        //拦截获取成员的操�?        _get = function(k) {
            console.log(k+"被读�?)
            return real[k];
        }

        //拦截写入成员的操�?        _set = function (k,v) {
            console.log(k+"被修改值为"+v)
            real[k]=v; //删除这句代码就创建了一个只读表
        }
    };

    return proxy;
}

//创建表对�?var tab = {x=12;y=15};

//创建一个代理表，以管理�?tab 的存取访�?var proxy = createProxy(tab);

//显示 "x被读�?
var c = proxy.x;

//显示 "y被修改值为19"
proxy.y = 19;

console.pause();

```

这里用到�?[函数闭包](../../function/closure.html) 保存 real,proxy 这些表对象�?
如果是写库文件，通常会用类（ class ）来做类似的事。因�?class 本身也可以作为名字空间使用，写库比较方便。参考： [class](../../class/class.html)

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/language-reference/datatype/table/meta.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/language-reference/datatype/table/meta.md')

