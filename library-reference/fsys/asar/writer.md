[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# fsys.asar.writer 库模块帮助文�?
## fsys.asar 成员列表

### fsys.asar.writer()

创建asar文件打包生成�?
[返回对象:fsysAsarWriterObject](#fsysAsarWriterObject)

## fsysAsarWriterObject 成员列表

### fsysAsarWriterObject.add()

添加文件或目录到asar文件

### fsysAsarWriterObject.allFiles

所有准备添加到asar文件中的文件路径

### fsysAsarWriterObject.clear()

清空所有文�?
### fsysAsarWriterObject.createInfo()

创建文件目录,成功返回this.info

失败返回null,错误信息

### fsysAsarWriterObject.eachPack(输出路径,buffer)

```aardio aardio
for(path,size,progress in fsysAsarWriterObject.eachPack("/test.asar")){
    /*path为正在处理的文件相对路径
size是已处理的文件大�?progress是进�?0�?之间的小�?输出路径必须使用.asar后缀,可选在参数@2中指�?buffer*/
}

```

### fsysAsarWriterObject.filter

```aardio aardio
fsysAsarWriterObject.filter = function(path){
    return /*参数为待添加文件路径,返回布尔值控制是否继续添�?/;
}

```

### fsysAsarWriterObject.info

createInfo函数生成的asar文件目录

### fsysAsarWriterObject.lasterr

执行成功此属性为�?否则是错误信�?
### fsysAsarWriterObject.pack(输出路径)

直接打包为asar文件

输出路径必须使用.asar后缀

如果需要获取进�?请使用eachPack迭代�?
### fsysAsarWriterObject.remove()

在已添加的asar的文件列表中移除文件或目�?
返回删除的文件数�?
### fsysAsarWriterObject.rootDirectory

指定根目�?如果不指定则自动生成此属�?
自动生成规则为：

所有添加的文件路径中取最短路�?如果是目录则设为根路�?

否则将其父目录设为根路径

### fsysAsarWriterObject.totalSize

在写入asar文件之前,totalSize会更新为所有文件的字节数总和

### fsysAsarWriterObject.treeData()

对已添加的文件生成可在treeview控件中显示的数据�?
[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/fsys/asar/writer.md)

