[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# 换行规则

## 回车换行�?
在计算机出现前有一种电传打字机（Teletype Model 33）每秒可以打 10 个字符，但是换行的要用去 0.2 秒，如果换行同时又有新的字符传过来就会丢失。于是研制人员就在每行后面加了两个。一个叫做“回车”，指示打印头移回左边；另一个叫做“换行”，指示打印机将纸下移一行�?
- 回车，Carriage Return, 简�?CR，字节码�?0x0D�?3），�?aardio 里表示为 `'\r'`�?- 换行，Line Feed, 简�?LF，字节码�?0x0A�?0），�?aardio 里表示为 `'\n'`

后来，计算机发明了，这两个概念也就被搬到了计算机上。那时，存储器很贵，一些科学家认为在每行结尾加两个字符太浪费了，加一个就可以。于是就出现了分歧�?
- Unix 系统里，每行结尾只有换行，即 `'\n'`�?- Mac 系统里，每行结尾是回车，�?`'\r'`�?
- Windows 系统里面，每行结尾是回车换行，即 `'\r\n'`�?
当然，这只是基础规则，应用程序当然也可以自行兼容这些不同的换行规则�?
�?aardio 中可使用 string.crlf() 函数将不同的换行风格规范化为指定的、统一的换行风格�?
## 读写文件的文本模�?
�?Windows 中默认以 `'\r\n'` 表示文本换行�?
在读写文本文件时，如果指定文本模式则读取文件时会自动将回车换行转换为 `'\n'`,而在写入时又自动�?`'\n'` 转换�?`'\r\n'` �?
例如在使�?io.file 函数打开文件�?可以在模式参数指�?b'标记启用二进制模式，指定't'标记则启用文本模�?这是默认设置)。具体请参�? [io.file 函数](../../library-guide/builtin/io/file.html)

## 文本框、富文本框的不同换行规则

在窗口程序中，要注意以下规则：aardio

- 文本框（edit）控件使�?`'\r\n'` 表示换行�?- 富文本框（richedit）控件使�?`'\n'` 表示换行�?
相关文档�?
- [edit 控件参考](../../library-reference/win/ui/ctrl/edit.html)
- [richedit 控件参考](../../library-reference/win/ui/ctrl/richedit.html)

## 在字符串中表示回车换�?
aardio 有多种表示字符串的方法，而这些表示方法都有预定义的回车换行解析规则。无论在 aardio 源代码里字符串是�?`'\r'`�?`'\n'`�?`'\r\n'` 哪一种风格换行，aardio 都会按下面的规则将其规范化为一致的结果:

- 放到双引�?\\" 或反引号 \` 中的字符串可以包含回车符与换行符，但不同风格的换行总是解释为统一以单�?`'\n'` 换行的字符串，示例：


  ```aardio aardio
  str = "我后面没有回车符
  我前面是换行�?

  ```

- 放到单引号中的字符串忽略所有原始的回车换行符，只能使用 `'\r'`, `'\n'` 或�?`'\r\n'` 这种转义符格式表示回车与换行符。示例：


  ```aardio aardio
  str ='我后面没有回车也没有换行
  我前面没有回车也没有换行'

  ```

- 在赋值语句中以块注释表示的字符串，保证换行总是被规范化为为 `'\r\n'` 。示例：


  ```aardio aardio
  str = /*
  我后面是回车�?  我前面是换行�?  */

  ```

- 在赋值语句以单行注释表示的字符串不会包含回车换行。示例：


  ```aardio aardio
  str = //这个字符串不包含回车符，也不包含换行�?
  ```


[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/language-reference/datatype/newline.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/language-reference/datatype/newline.md')

