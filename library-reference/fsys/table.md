[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# fsys.table 库模块帮助文�?
## fsys 成员列表

### fsys.table

支持�?table 对象自动序列化为硬盘文件�?
fsys.table 可作为普�?table 对象使用�?
在线程退出时将会同步存储到文件中�?
一般建议直接使�?fsys.config

### fsys.table("/config/setting.table",默认配置�?)

创建 table 对象，在线程退出时将会同步存储到文件中�?
可选使�?参数@2 指定一�?table 对象指定字段的默认值�?
fsys.table 并非实时读写，而是将配置读入内存�?
所以请不要多对象、多线程、多进程打开同一配置文件�?
这会导致多份不同步的配置写入存储设备时会相互覆盖�?
注意此对象不可跨线程传递�?
多线程可通过 winform 成员函数转发到界面线程操作配置文件即可，

多进程可利用原子窗体、进程互斥体避免冲突

### fsys.table()

[返回对象:fsysTableObject](table.html#fsysTableObject)

## fsysTableObject 成员列表

### fsysTableObject.?

自配置文件读写属性�?
使用 table.tostring 函数序列化配置表�?
仅序列化以字符串、数值为键的元素�?
仅序列化值为字符串、数值、buffer 以及定义�?\_serialize 元方法的成员�?
循环引用的值转换为 null，序列化时忽略成员函数�?
配置文件在首次使用时自动加载,退出程序时自动保存.

### fsysTableObject.afterLoad

指定一个函�?在下次重新加载配置文件时调用

此函数默认为空函�?在调�?winform.bindConfig 后会被自动赋值用于写入控件�?
### fsysTableObject.assign()

[返回对象:fsysTableObject](table.html#fsysTableObject)

### fsysTableObject.assign(混入�?

```aardio aardio
fsysTableObject.assign(
   键名 = �?
   键名2 = �?
);//该数会自动调�?save 函数保存配置到文�?
```

### fsysTableObject.beforeSave

指定一个函�?在保存配置以前自动调�?
此函数默认为空函�?在调�?winform.bindConfig 后会被自动赋值用于读取控件�?
### fsysTableObject.load()

从文件载�?
加载成功返回对象,加载失败返回null空�?
[返回对象:fsysTableObject](table.html#fsysTableObject)

### fsysTableObject.mix()

[返回对象:fsysTableObject](table.html#fsysTableObject)

### fsysTableObject.mix(混入默认值表)

```aardio aardio
fsysTableObject.mix(
   键名 = 默认�?
   键名2 = 默认�?
);//该函数用于设定默认�?但不会修改已存在的�?
```

### fsysTableObject.save()

存储到文�?
在线程退出时也会自动调用该函�?
[返回对象:fsysTableObject](table.html#fsysTableObject)

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/fsys/table.md)

