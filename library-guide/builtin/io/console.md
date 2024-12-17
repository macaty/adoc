[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# 控制�?
控制台程序在命令行窗口执行，没有图形界面�?
io 库函数虽然可以操作控制台，但使用专门针对控制台开发的 console 库更方便功能也更多�?
## 打开关闭控制台窗�?
- io.open() 打开控制台窗�?
此函数用于控制台窗口�?除可选用第二个参数指定控制台窗口标题以外，请不要指定其他参数�?
当指定第一个调用参数时，此函数将与 io.file 执行完全相同的操作，这种用法�?aardio 新版本中已被废弃�?
这是一个较低层的函数，建议使用基于 io.open �?console.open 函数打开控制台窗口。console 提供了更多的功能�?
- console 的很多库函数可自动按需调用 console.open
- console.open 不会�?io.open 那样重置控制台并清除之前输出的内�?- console.open 将更好地设置的控制台选项
- console.open 会自动重定向 msvcrt.dll 的标准输入输出流
- console.open 执行时自动发�?afterConsoleOpen 消息，aardio 中的一些库会响�?afterConsoleOpen 消息并自动重定向标准输入输出到控制台。例�?py3 扩展库，dotNet 支持库等�?console.open 被调用后可自动将 Python,.NET 的标准输入输出重定向到控制台�?
�?io.open() 函数并没有这些功能�?
### io.close()

关闭控制台窗口。注意在程序退出时会自动关闭控制台，所以在程序结束时调�?`io.close()` 是多余且不必要的�?
如果程序使用�?console 库函数，则应使用 console.close 替代 io.close 函数�?
## 标准输入输出对象

aardio 中的标准输入输出对象如下�?
- io.stdout 标准输出对象�?
- io.stdin 标准输入对象�?
- io.stderr 标准错误输出对象�?
这些对象都是 io.file 文件对象，请参考：

- [io.file 指南](file.html)
- [io.file 手册](../../../library-reference/io/_.html#ioFileObject)

默认的用 import console; 打开控制台窗口以后， 标准输入输出对象将自动重定向到控制台窗口。标准输入对象可以读取用户输入，而标准输出可以向控制台窗口输出内容�?
## 自控制台读取文本

1. 函数原型


   ```aardio aardio
   var str = io.getText( 缓冲区大�?100 )
   var str = io.getText()

   ```

2. 函数说明


从控制台读取用户输入文本，用户输入后回车换行则该函数返回.

此函数功能类�?io.stdin.read() ，但控制台的编码环境较为复杂，使�?io.getText() 读取控制台文本可以更好地支持 Unicode 字符�?
如果导入�?console 库，建议使用基于 io.getText 实现�?console.getText 函数。console.getText 可以指定输入提示文本，也可以自动打开控制台，�?io.getText 并不提供这些功能�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-guide/builtin/io/console.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-guide/builtin/io/console.md')

