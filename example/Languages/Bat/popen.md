[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 进程管道读写

```aardio aardio
//命令行管�?//相关范例：进�?> 管道
import win.ui;
/*DSG{{*/
var winform = win.form(text="进程管道读写";right=759;bottom=469)
winform.add(
edit={cls="edit";left=15;top=11;right=743;bottom=446;edge=1;hscroll=1;multiline=1;vscroll=1;z=1}
)
/*}}*/

import process.popen

/*
打开命令�?隐藏命令行窗口，并返回可读写的进程管道�?
参数@2 可用字符串指定进程启动参数，多个参数用空格分格�?如果 参数@3 是字符串，则�?参数@2 开始合并参数，并以空格分开，单参数含空格或需转义时首尾添加双引号�?*/
var prcs,err = process.popen("cmd.exe","/k chcp "+::Kernel32.GetACP())
if(!prcs) return winform.msgboxErr(err);

//如果调用 UTF8 编码的程序，请添加下面的编码声明
//prcs.codepage = 65001

var cmd = /*
CD C:\
C:
dir
mkdir test
rmdir test
*/

//写管�?prcs.write(cmd)

//读管道直接到指定字符串结束，不阻塞当前线程窗口消息�?var result = prcs.peekTo(">");

//输出到文本框
winform.edit.print(result);

//输入命令加换�?prcs.print('exit');

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Bat/popen.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Bat/popen.md')

