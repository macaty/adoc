[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# aardio 模板语法

aardio 语言内置的模板语法规则如下：

- aardio 代码如果�?HTML 代码开始，或代码包�?`<?` �?`?>` 标记则启用模板语法。部分库模块中支�?aardio 模板语法的函数可能要求字符串参数�?`<?` �?`?>` 标记开始才会启�?aardio 模板语法�?
- aardio 代码可以是纯 aardio 代码，也可以是纯 HTML，或者是 HTML、aardio 相互混合的模板代码�?
- 启用模板语法�?aardio 代码，纯 aardio 代码必须置于开始标�?`<?` �?结束标记 `?>` 之间�?aardio 将不�?`<? ..... ?>` 之内的部分作为字符串参数并调用全局函数 print 函数输出�?
- aardio 总是忽略代码文件开始的空白字符（包含空格、制表符，换行），不会将文件开始的空白字符作为模板数据输出�?
- aardio 文件只能�?UTF-8 编码保存，不建议添加 UTF8 BOM。如果文件添加了 BOM，aardio 仍然会自动移�?BOM 不会�?BOM 头作为模板数据输出�?
- 模板开始标�?`<?` 必须独立，不能紧跟英文字母。例�?`<?xml...` 不被解析�?aardio 代码段开始标记�?
- 可以使用 `<?=表达�?>` 输出文本 \- 作用类似�?print( 表达�?)，可用逗号分隔多个表达式�?aardio 会忽略表达式前面等号首尾的空白字�?, 下面的写法也是允许的�?

  ```aardio aardio
  <?
  = 表达�?,表达�?
  ?>

  ```

- 模板输出函数 print 使用规则�?
  aardio 代码在解析模板语法时，将自动调用全局 print 函数�?`..print` ）输出数据�?

  - aardio �?print 函数只能用于捕获或修改模板输出，此函数不可随意改动指向，应交由负责模板输出的框架自动管理�?  - print 函数随时可能被动态指向不同的模板输出函数，非必要不建议在普通代码中直接使用 print 函数。也不应保存 print 函数到其他变量后再进行调用。例如在服务端网页开发时，建议直接调�?response.write 而不是调�?print 函数�?  - print 允许接收多个参数，并且必须对每个参数调用 `tostring()` 将参数转换为字符串�?  - 在一个独�?aardio 模板文件解析结束时，print 函数将收到一�?null 参数调用，print 函数应当在此时完成输出操作�?
print 函数可能被负责模板输出的库或框架重新定义并指向不同的实际函数，以实现不同的模板输出应用。例如在 HTTP 服务端中 print 将自动指�?response.write 函数。而在调用 string.loadcode �?print 将临时指向拼接字符串的代码， 请在内置�?builtin.string 中查�?string.loadcode 函数的源代码，以了解如何通过自定�?print 函数捕获或修改模板输出�?
如果没有调用任何修改 print 函数的库或函数，在默认情况下�?
  - 如果在开发环境中且首次调用模板或 print 输出的是 HTML 代码，则创建网页浏览器控件并显示�?HTML 代码生成的网页内容�?  - 否则 print 函数将默认调�?io.print 函数向控制台窗口输出内容。print 函数在默认调�?io.print 前会自动打开控制台，之后在退出非界面线程( 指未导入 win.ui 的线�?) 前会暂停控制台�?
可以粘贴下面的示例代码到 aardio 编辑器中然后�?F5 直接运行以预览模板输出效果：

```aardio aardio
<!doctype html>
<html><head><meta charset="utf-8"><title>帮助页面</title></head>
<body>当前时间<? = time() ?>
</body></html>

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/language-reference/templating/syntax.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/language-reference/templating/syntax.md')
