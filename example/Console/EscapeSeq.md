[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 控制台程序范�?- ANSI 转义

```aardio aardio
//控制台程序范�?- ANSI 转义
import console.ansion;

console.log('
\e[30m 字体黑色
\e[31m 字体红色
\e[32m 字体绿色
\e[33m 字体黄色
\e[34m 字体蓝色
\e[35m 字体洋红�?\e[36m 字体青色
\e[37m 字体白色

\e[40m 黑色背景
\e[41m 红色背景
\e[42m 绿色背景
\e[43m 黄色背景
\e[44m 蓝色背景
\e[45m 洋红色背�?\e[46m 青色背景
\e[47m 白色背景

\e[40;1m 亮黑色背�?\e[41;1m 亮红色背�?\e[42;1m 亮绿色背�?\e[43;1m 亮黄色背�?\e[44;1m 亮蓝色背�?\e[45;1m 亮洋红色背景
\e[46;1m 亮青色背�?\e[47;1m 亮白色背�?
\e[0m 恢复默认样式

\e[4m 下划�?\e[1m 粗体
\e[7m 反色

\e[0m 恢复默认样式

光标上移2行：\e[2A
光标下移2行：\e[2B
光标右移2字符：\e[2C
光标左移2字符：\e[2D
');

console.pause(true);

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Console/EscapeSeq.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Console/EscapeSeq.md')
