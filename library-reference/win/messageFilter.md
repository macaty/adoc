[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# win.messageFilter 库模块帮助文�?
## win.messageFilter 成员列表

用于管理权限进程设置消息特权隔离白名�?
### win.messageFilter.change(窗口句柄,选项,消息,...)

变更消息特权隔离白名�?成功返回true,

如果不指定窗口句柄则设置进程级白名单

### win.messageFilter.change(窗口句柄,阻止选项,消息)

```aardio aardio
win.messageFilter.change(,1/*_MSGFLT_ADD*/
    ,0x4A/*_WM_COPYDATA*/,0x233/*_WM_DROPFILES*/,0x0049/*_WM_COPYGLOBALDATA*/ )

```

### 自动完成常量

\_MSGFLTINFO\_ALLOWED\_HIGHER=3

\_MSGFLTINFO\_ALREADYALLOWED\_FORWND=1

\_MSGFLTINFO\_ALREADYDISALLOWED\_FORWND=2

\_MSGFLTINFO\_NONE=0

\_MSGFLT\_ADD=1

\_MSGFLT\_ALLOW=1

\_MSGFLT\_DISALLOW=2

\_MSGFLT\_REMOVE=2

\_MSGFLT\_RESET=0

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/win/messageFilter.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/win/messageFilter.md')

