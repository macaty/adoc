[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# fsys.drives 库模块帮助文�?
## fsys.drives 成员列表

逻辑分区相关函数�?
相关库：sys.volume , sys.storage

### fsys.drives.each(driveType)

```aardio aardio
for drive,driveType in fsys.drives.each() {
    /*按字母序遍历所有逻辑分区,
可选在参数中用一个数值指定分区类�?例如 _DRIVE_FIXED,
返回�?drive 为盘�?以冒号结�?
driveType 为分区类�?请参�?::Kernel32.GetDriveType 的文�?*/
}

```

### fsys.drives.eachFixed()

```aardio aardio
for drive in fsys.drives.eachFixed() {
    /*按字母序遍历所有硬盘逻辑分区,
迭代变量 drive 为盘�?以冒号结�?
注意 USB 硬盘也会遍历�?
但忽略普�?U�?
可使�?sys.storage.isUsbDevice 函数检�?USB 存储设备*/
}

```

### fsys.drives.eachRemovable()

```aardio aardio
for drive in fsys.drives.eachRemovable() {
    /*按字母序遍历所有移动盘逻辑分区,这个一般指的是 U�?
迭代变量 drive 为盘�?以冒号结�?
可使�?sys.storage.isUsbDevice 函数检测是�?USB 存储设备*/
}

```

### fsys.drives.free()

返回首个未使用的可用盘符

### fsys.drives.get()

返回包含所有逻辑分区的数�?按字母排�?

可选用参数@1指定包含所有可用分区的数组,

可选用参数@2 指定分区类型,

可用分区类型请参�?::Kernel32.GetDriveType 的文�?
### fsys.drives.getFixed()

返回包含所有硬盘逻辑分区的数�?按字母排�?

包含 USB 硬盘但不包含 U�?

可使�?sys.storage.isUsbDevice 函数检�?USB 存储设备\*/

### fsys.drives.getRemovable()

返回包含所有移动盘逻辑分区的数�?按字母排�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/fsys/drives.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/fsys/drives.md')

