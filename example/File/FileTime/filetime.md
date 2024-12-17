[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 读写文件时间

```aardio aardio
//读写文件时间
import fsys.file;
import console;

//定义测试用文件路�?var filePath = io._exepath;

//最简单的获取文件修改时间（time 对象）的方法
var tm = fsys.file.lastModified(filePath);
console.log(tm);

//打开文件
var file = fsys.file(filePath,"r");

//显示�?2个字节的内容
console.log( file.read(12) );

//返回文件时间，返回对象为一个表，包�?write, creation, access 三个字段
var tms = file.getTime();

//显示文件创建时间（time 对象�?console.log( tms.write );

//创建时间增加48小时
tms.write.addhour(48);

//修改文件时间
file.setTime(tm);

//返回 FILETIME 格式时间，返回对象为一个表，包�?write, creation, access 三个字段
var ftm = file.getFileTime();

//显示文件创建时间（fsys.time 对象 )
console.log( ftm.write )

//如果忘记关闭文件,在程序退出时会自动关�?file.close()
console.pause();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/File/FileTime/filetime.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/File/FileTime/filetime.md')

