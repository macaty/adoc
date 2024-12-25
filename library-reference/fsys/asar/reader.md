[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# fsys.asar.reader 库模块帮助文�?
## fsys.asar 成员列表

asar是electron里的一种打包文件格�?
### fsys.asar.reader

asar是electron里的一种打包文件格�?
asar格式文件解析�?
支持内存文件,资源文件,硬盘文件�?
支持解析asar格式文件，直接加载到treeview控件，单独提取文件，

提取全部文件并获取展开进度，支持直接编辑文件数据，

替换文件内容(不用解包再打�?

### fsys.asar.reader()

创建asar格式文件解析�?

参数中输入asar文件路径

[返回对象:fsysUnasarReaderObject](#fsysUnasarReaderObject)

## fsysUnasarReaderObject 成员列表

### fsysUnasarReaderObject.eachFile

```aardio aardio
for path,size,offset,executable,unpacked in fsysUnasarReaderObject.eachFile(){
    /*path:包含上层目录的相对路�?size:文件大小,已自动移动文件指针到文件所在的偏移位置
offset: 文件偏移位置,offset为null则为目录�?unpacked 文件,
executable:是否可执行文�?unpacked 为true的文件未包含在asar文件�?/
}

```

### fsysUnasarReaderObject.eachReadBuffer(缓冲�?文件路径)

```aardio aardio
for readSize in fsysUnasarReaderObject.eachReadBuffer(缓冲区对�?"要读取取的文件相对路�?) {
    /*迭代器的第一个参数应当是缓冲�?第二个参数可选指定要读取的文件相对路�?也可以指定要读取的大�?迭代变量 readSize 表示本次读取的长�?/
}

```

### fsysUnasarReaderObject.eachUnpack(解压目录,缓冲�?

```aardio aardio
for path,size,progress in fsysUnasarReaderObject.eachUnpack("/ExtractDir") {
    /*迭代器的第一个参数应指下要解压的目录
可选使用第二个参数定定缓冲区对�?path为当前正在处理的文件路径,size为已解包总大�?
progress是使用小数表示的进度,1为已完成
*/
}

```

### fsysUnasarReaderObject.enum

```aardio aardio
fsysUnasarReaderObject.enum(
    function(fileName,path,offset,size,executable,unpacked){
        /*fileName:文件�?path:包含上层目录的相对路�?offset:如果是包内文刚表示偏移位�?并已移动文件指针到这�?size:文件大小
executable:是否可执行文�?unpacked 是否外部 unpacked 目录下的文件*/
    }
)

```

### fsysUnasarReaderObject.files

文件信息列表,这是一个数�?
### fsysUnasarReaderObject.headerSize

asar文件头大

### fsysUnasarReaderObject.info

文件系统信息,这是一个树形结构的�?
### fsysUnasarReaderObject.read()

这个函数的参数与fsys.stream参数的read函数一样用�?

建议在这里指定要读取的长�?
不指定长度读取一行，但不可以指定负数

可以指定结构�?
### fsysUnasarReaderObject.readFile()

参数中指定文件的相对路径,

读取并返回文件的全部数据,返回值为字符串�?
### fsysUnasarReaderObject.readTo()

读取直到以参数指定的字符串结�?不包含束字符�?
这个函数会一直向后读,而不考虑是不是越过了当前的文件块

### fsysUnasarReaderObject.replace("文件相对路径",替换数据)

写入替换数据长度不能大于原数据长�?
### fsysUnasarReaderObject.replaceText("文件相对路径",替换数据)

替换文本并移除回车使�?

'单换�?
### fsysUnasarReaderObject.seek()

参数中指定文件的相对路径,

移动文件指针到此文件在asar文件中的开始位�?
失败返回 null

### fsysUnasarReaderObject.totalSize

asar中所有文件的大小,不包含asar文件头大�?
### fsysUnasarReaderObject.treeData()

返回可以直接加载到treeview视图的数据表

### fsysUnasarReaderObject.unpack(解压目录)

直接解压所有文件到指定目录�?
如果要获取解压的进度,建议使用eachUnpack迭代�?
## fsysUnasarReaderObject.this 成员列表

### fsysUnasarReaderObject.this.header

文件�?fsys.unasar.header结构�?
[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/fsys/asar/reader.md)

