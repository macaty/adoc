[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# fsys.res 库模块帮助文�?
## fsys.res 成员列表

### fsys.res.enum(回调函数,资源类型,模块句柄或路�?

```aardio aardio
fsys.res.enum(
    function(module,resType,resName){
        var res = string.load(resName,resType,module);
        return true;
    }
)

```

### fsys.res.free(dll句柄)

释放DLL

### fsys.res.load("DLL路径")

加载资源DLL并返回句�?
仅加载资源不会执行DLL代码

返回值可作为fsys.res.enum或string.load的最后一个参�?
注意必须调用fsys.res.free函数释放返回的句�?
### fsys.res.loadRes(资源�?资源类型,模块句柄或路�?

加载资源文件,返回buffer

除参数@1外的其他参数可省�?
### fsys.res.makeIntResource()

将数值类型资源名转换为指�?字符串类型名直接返回

### fsys.res.open()

[返回对象:fsysResUpdaterObject](#fsysResUpdaterObject)

### fsys.res.open(执行文件路径,是否删除旧的资源)

打开资源准备更新

### fsys.res.saveAppData(资源目录,目标目录)

保存内嵌资源目录到系统AppData目录

源目录可指定源目录路�?
目标目录必须指定子目录路�?不能指定完整路径,

所有参数可省略

### fsys.res.saveRes(源目�?目标目录)

保存内嵌资源目录为硬盘文�?
源目录可指定源目录路�?
所有参数可省略�?
资源路径自动转为大写（必须大写）�?
如果一定要小写，aardio 里可以打包解包的库太多了�?
例如: sevenZip.lzma.tar($"\\你要嵌入的打包文�?tar.lzma","\\运行时解包路�?)

## 全局对象 成员列表

### \_RT\_TYPELIB

```aardio aardio
"TYPELIB"

```

## fsysResUpdaterObject 成员列表

### fsysResUpdaterObject.close(是否丢弃更改)

关闭并更新资�?

参数可�?默认为false

### fsysResUpdaterObject.update(资源类型,资源�?数据)

更新或添加资�?
### 全局常量

### \_RT\_TYPELIB

```aardio aardio
"TYPELIB"

```

### 自动完成常量

\_RT\_ACCELERATOR=0x9

\_RT\_BITMAP=0x2

\_RT\_CURSOR=0x1

\_RT\_DIALOG=0x5

\_RT\_FONT=0x8

\_RT\_FONTDIR=0x7

\_RT\_GROUP\_ICON=0xE

\_RT\_ICON=0x3

\_RT\_MENU=0x4

\_RT\_RCDATA=0xA

\_RT\_STRING=0x6

\_RT\_VERSION=0x10

\_VS\_VERSION\_INFO=0x1

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/fsys/res.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/fsys/res.md')

