[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# fsys.fileInfo 库模块帮助文�?
## fsys 成员列表

### fsys.fileInfo()

[返回对象:fsysfileinfoObject](#fsysfileinfoObject)

### fsys.fileInfo(文件或目录路�?

获取文件信息,唯一ID�?
即使传入空路径，或不存在的路�?都会返回对象(但id属性为�?,

可用于判断文件路径是否指向同一真实文件

## fsys.fileInfo 成员列表

获取文件信息(包含唯一ID)

### fsys.fileInfo.same(文件路径,文件路径2)

检测两个文件路径是否指向同一真实文件

## fsysfileinfoObject 成员列表

### fsysfileinfoObject.accessTime

文件最后访问时�?
!filefiletimes.;

### fsysfileinfoObject.attributes

文件属性，数�?
### fsysfileinfoObject.creationTime

文件创建时间

[返回对象:filefiletimesObject](#filefiletimesObject)

### fsysfileinfoObject.id

文件唯一ID，字符串�?
可用于唯一标识一个硬盘文�?
### fsysfileinfoObject.index

文件索引,math.size64对象

[返回对象:mathSize64Object](../math/_.html#mathSize64Object)

### fsysfileinfoObject.numberOfLinks

链接�?
### fsysfileinfoObject.size

文件大小,math.size64对象

[返回对象:mathSize64Object](../math/_.html#mathSize64Object)

### fsysfileinfoObject.volumeSerial

所在分区序列号

### fsysfileinfoObject.writeTime

文件最后修改时�?
[返回对象:filefiletimesObject](#filefiletimesObject)

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/fsys/fileInfo.md)

