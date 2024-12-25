[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# win.version 库模块帮助文�?
## win 成员列表

### win.version

系统版本信息

aardio 内建以下全局常量也可用于检测系统版本：

\_WINXP,\_WIN7\_LATER,\_WIN10\_LATER,\_WINE,

\_WIN\_VER\_MAJOR,\_WIN\_VER\_MINOR,\_WIN\_VER\_BUILD �?
[返回对象:winVersionObject](#winVersionObject)

## winVersionObject 成员列表

### winVersionObject.buildNumber

操作系统的构建版本号

### winVersionObject.csdVersion

关于该操作系统的附加信息

### winVersionObject.displayVersion

用于显示的版本号,

默认显示为主版本�?\+ "." \+ 副版本号

如果导入�?win.versionEx�?
Win 10,Win 11 显示�?字符发行时间,

�?位数字为年份,春季加H1,秋季加H2

Win10 20H2 以前返回�?位为月份�?Release ID

### winVersionObject.format()

格式化为文本格式的版本号

### winVersionObject.isServer

是否服务器版本系�?
### winVersionObject.isVista

是否 Vista

### winVersionObject.isVistaLater

当前系统是否 Vista 以及 Vista 以后的版�?
该值如果为false,即为 Win xp, Win 2003操作系统

### winVersionObject.isWin10Later

当前系统是否 Win 10以及 Win 10以后的版�?
### winVersionObject.isWin11Later

当前系统是否 Win 11以及 Win 11以后的版�?
注意 Windows 11 的主版本号仍然是 10

### winVersionObject.isWin7

是否 win7

### winVersionObject.isWin7Later

当前系统是否 Win 7以及 Win 7以后的版�?
### winVersionObject.isWin8

是否 win8

### winVersionObject.isWin8Later

当前系统是否 Win 8以及 Win 8以后的版�?
### winVersionObject.isXp

是否 Win XP

### winVersionObject.majorVersion

操作系统的主版本�?
注意 Windows 11 的主版本号仍然是 10

### winVersionObject.minorVersion

操作系统的副版本�?
### winVersionObject.name

操作系统产品名称,例如

"Windows XP"

"Windows 7"

"Windows 2012 R2"

### winVersionObject.platformId

平台ID

### winVersionObject.productType

产品类型,多个选项按位�?
普通家用操作系统\_VER\_NT\_WORKSTATION

服务器操作系统\_VER\_NT\_SERVER,\_VER\_NT\_DOMAIN\_CONTROLLER

### 自动完成常量

\_VER\_EQUAL=0x1

\_VER\_GREATER\_EQUAL=0x3

\_VER\_MAJORVERSION=0x2

\_VER\_MINORVERSION=0x1

\_VER\_NT\_DOMAIN\_CONTROLLER=0x2

\_VER\_NT\_SERVER=0x3

\_VER\_NT\_WORKSTATION=1

\_VER\_PRODUCT\_TYPE=0x80

\_VER\_SERVICEPACKMAJOR=0x20

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/win/version.md)

