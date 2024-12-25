[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 中使�?Python 数�?
```aardio aardio
//aardio 中使�?Python 数�?import console;
import py3;

//aardio 数值传�?Python 会默认转为浮点数
//如果要创�?Python 整数请使�?py3.int 函数，例�?
var pyInt = py3.int("12355678901235567890")

//支持 aadio 中的常用运算�?注意这些运算符返回的都是 py3.object 对象
console.log( pyInt+py3.int("12355678901235567890") );
console.log( pyInt%3 );
console.log( pyInt==3 );
console.log( -pyInt );

//可用 tostring() 转换为字符串,
//注意 console.log() 已对所有参数调�?tostring() 转为字符�?console.log( tostring(pyInt) )

//创建 Python 浮点�?var pyFloat = py3.float("12355678901235567890")

//支持常用运算�?var pyFloat = pyFloat / 0xFFFFFF;

//转换为普�?aardio 数�?var num = tonumber(pyFloat);

//调用 Python 内建函数转换数�?var num = py3.builtin.abs(-12);

console.log(num);
console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python 3.x/number.md)

