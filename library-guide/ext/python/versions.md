[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# 选择不同版本 Python 运行�?
aardio 提供了自带不�?Python 运行时版本的 Python 扩展库�?
可用 import 语句导入指定版本 Python 扩展库示例：

- `import py3;` 导入 Python 3.8 扩展库，支持 Win7 �?Win7 以上系统
- `import py3.4;` 导入 Python 3.4 扩展库，支持 XP �?XP 以上系统
- `import py3.10;` 导入 Python 3.10 扩展库，支持 Win10 �?Win10 以上系统
- `import py2;` 导入 Python 2.7 扩展库，支持 XP �?XP 以上系统

推荐使用更通用�?py3 扩展库�?
要点�?
- 在一�?aardio 程序中，不应导入多个不同版本�?Python 扩展库，
- aardio 中所�?Python 扩展库都自带绿色 Python 运行时�?
使用 Python 扩展库时应去掉扩展库副版本号，例如：

```aardio aardio
import py3.4;
console.log( py3.version );

```

要特别注�?`py3.4` 只是库名称，导入的是 `py3` 对象�?`py3.4` 不是符合语法的标识符�?
因为 aardio 程序�?32 位，上面所�?Python 扩展库都�?32 位�?
aardio 提供�?process.python 扩展库可支持任意版本 Python�?
process.python 的主要特点：

- 兼容 32�?64�?Python 运行时�?- 可自�?Python 运行时，也可以支持系统安装的 Python 运行时�?
请参考范例： [调用 Python 任意版本](../../../example/Languages/Python/Python AnyVersion/QuickStart-1.html)

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-guide/ext/python/versions.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-guide/ext/python/versions.md')

