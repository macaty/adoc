[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# win.versionEx 库模块帮助文�?
## win 成员列表

### win.versionEx

导入�?win.versionEx 指向 win.version 并进行扩�?

增加 productName,editionId,updateBuildRevision 等字�?

增强 format 函数,以及改变 displayVersion �?Win10,Win11 格式

aardio 内建以下全局常量也可用于检测系统版本：

\_WINXP,\_WIN7\_LATER,\_WIN10\_LATER,\_WINE,

\_WIN\_VER\_MAJOR,\_WIN\_VER\_MINOR,\_WIN\_VER\_BUILD �?
[返回对象:winVersionObject](#winVersionObject)

## winVersionObject 成员列表

### winVersionObject.editionId

版本ID，例�?"Professional","ServerStandard"等等

需要导入win.versionEx此属性才可用

### winVersionObject.isWin10ReleaseLater()

参数指定 Win10 Release ID,

Release ID �?2 位为年份，后 2 位为发行月份,

因为最后一个使�?Release ID 的系统为 Win10 2009�?0H2�?

Win10 20H2 以及之后的系统总是返回 true

需要导�?win.versionEx 此函数才可用

### winVersionObject.productName

产品名称,例如"Windows 10 Pro","Windows Server (R) 2008 Standard"等等

需要导入win.versionEx此属性才可用

### winVersionObject.updateBuildRevision

更新小版本号

需要导�?win.versionEx 此属性才可用

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/win/versionEx.md)

