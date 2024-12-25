[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# loadcodex 函数

loadcodex() 函数可用于直接运�?aardio 代码�?aardio 代码文件�?
1. 函数原型�?
   `返回值列�?= loadcode( codeString | filepath | function [�?..] )`

2. 函数说明�?
   参数 @1 可以是包�?aardio 代码的字符串值，也可以是 aardio 代码文件的路径，路径可以用斜杠作为首字符表示应用程序根目录。参�?@1 也可以直接指定一个函数对象�?
   此函数立即执行参�?@1 指定的代码或函数，并将其他参数作为调用参数。返回被调用代码与函数的返回值�?
   一个类似的函数�?[eval](eval.html) 函数。eval 立即运行代码，并将代码作为一个普通表达式计算并返回值，eval 会抛出异常而不是返回错误信息，并且 eval 不支持指�?aardio 代码文件路径作为参数.

3. 调用示例�?

   ```aardio aardio
   //生成一个测试用代码文件
   string.save("/.test.aardio","
   var a,b = ...;//文件也是一个匿名函�?可以这样接收参数
   return a,b
   ");

   //加载代码文件返回一个函数对�?   var a,b = loadcodex("/.test.aardio","a参数","b参数")

   ```


[Markdown 格式](https://www.aardio.com/zh-cn/doc/language-reference/builtin-function/loadcodex.md)

