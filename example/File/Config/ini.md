[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: ini 文件

```aardio aardio
//ini 文件
import console;
import fsys.ini;

//打开文件,支持内嵌资源文件
//如果文件不存在则自动创建新文�?var ini=fsys.ini("\配置文件.ini")

/*
fsys.ini 使用 UTF-8 编码读写 ini 文件�?但操作系统自动转换为 ANSI 编码存储�?
用记事本打开空的 ini 文件在存储选项里看�?UTF-8 编码并非因为空文件是 UTF-8 编码�?用其他软件打开 ini 文件写非 ANSI 编码存进去，再用程序读写当然就会乱码�?
这不是因�?ini 很奇怪地一会是 UTF-8，一会是 ANSI 编码�?ini 是很古老的格式，足够成熟，�?ini 格式要有基本的信任�?
如果不是为了兼容原来�?ANSI 程序，不必要使用 ini 文件格式�?web.json, fsys.config 这些格式使用的都�?UTF-8 编码，使用也更方便�?*/

//读取小节对象
sec = ini.getSection("小节名称")

//读写�?sec.项名�?= 123;
console.dump(sec)

//保存
sec.save()

console.pause();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/File/Config/ini.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/File/Config/ini.md')

