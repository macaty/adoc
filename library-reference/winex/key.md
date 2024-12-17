[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# winex.key 库模块帮助文�?
## winex.key 成员列表

### winex.key.altClick(句柄,"键名")

后台发�?ALT 组合键击键消息，可指定一个或多个键名或虚拟键值参数�?
如果目标窗口是外部线程应先使�?winex.attach 共享输入处理机制�?
个别按键操作可能需要先�?win.setActive 激活目标窗口（不常见）

### winex.key.altDown(句柄,"键名")

后台发�?ALT 组合键按下消�?
参数二可以是键名或虚拟键�?
### winex.key.altUp(句柄,"键名")

后台发�?ALT 组合键弹起消�?
参数二可以是键名或虚拟键�?
### winex.key.click(句柄,"键名")

参数二可以是键名或虚拟键�?
### winex.key.combine(hwnd,"CTRL","字符串参�?)

发送组合热�?参数个数不限.

参数可以是键名字,或者按键的虚拟�?\_VK前缀常量)

如果目标窗口是外部线程应先使�?winex.attach 共享输入处理机制�?
个别按键操作可能需要先�?win.setActive 激活目标窗口（不常见）

### winex.key.delayClick

完整击键之间的间�?默认�?

### winex.key.delayDown

按下后的时间间隔,默认�?

### winex.key.delayUp

弹起后的时间间隔,默认�?

### winex.key.down(句柄,"键名")

参数二可以是键名或虚拟键�?
### winex.key.send(句柄,"TEST")

输入ASCII字符

### winex.key.up(句柄,"键名")

参数二可以是键名或虚拟键�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/winex/key.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/winex/key.md')

