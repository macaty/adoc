[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 操作 Python 字符�?
```aardio aardio
//aardio 操作 Python 字符�?import console;
import py3;

//创建 Python 字符�?var pyStr = py3.str("字符�?); //返回一�?py3.object 对象
console.log( pyStr.toStr()  ); //转为 Python 字符串，返回一�?py3.object 对象

console.log( pyStr.toString()  ); //转为 aardio 字符�?Pyton 字节数组转为 buffer
console.log( tostring(pyStr)  ); //转为 aardio 字符�?实际就是调用 yStr.toString()
console.log( pyStr ); //console.log 已经默认调用�?tostring()

//parseValue() 也可以获取纯字符�?
//区别�?pyStr.toString() 遇到字符串之外的 Python 类型时也会尝试自动转换为字符�?console.log( pyStr.parseValue() )
console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python 3.x/str.md)

