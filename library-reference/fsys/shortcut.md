[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# fsys.shortcut 库模块帮助文�?
## fsys 成员列表

### fsys.shortcut

快捷方式生成�?
### fsys.shortcut("目标文件根目�? )

创建快捷方式生成�?
快捷方式参数可指定相对\[目标文件根目录\]的子路径

### fsys.shortcut()

[返回对象:fsysShortcutObject](#fsysShortcutObject)

## fsysShortcutObject 成员列表

### fsysShortcutObject.create( 参数�?)

```aardio aardio
fsysShortcutObject.create(
    url = "网址";
    lnk = "应用程序路径";/*lnk,url必须且只能指定其中一�?其他参数都是可选的可以省略*/
    arguments = 启动参数;
    filename = 快捷方式文件�?
    icon = 应用程序路径图标或图标资源所在程序路�?
    iconIndex = 0;
    taskBar = true;
    startMenu = false;
    desktop = true;
    programsFolder = "\公司名\";
    allUsers = false;
)

```

### fsysShortcutObject.delete( 参数�?)

```aardio aardio
fsysShortcutObject.delete(
    url = "网址";
    lnk = "应用程序路径";/*lnk,url必须且只能指定其中一�?其他参数都是可选的可以省略*/
    filename = "快捷方式文件�?;
    taskBar = true;
    startMenu = false;
    desktop = true;
    programsFolder = "\公司名\";
)

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/fsys/shortcut.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/fsys/shortcut.md')

