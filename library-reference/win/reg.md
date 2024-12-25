[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# win.reg 库模块帮助文�?
## win 成员列表

### win.reg()

[返回对象:winRegObject](#winRegObject)

### win.reg(path)

打开或创建注册表路径�?
@path 参数指定注册表路径�?
此函数还有其他可选参数，一般不必指�?
### win.reg(path,true)

仅打开已存在的注册表路径，

@path 参数指定注册表路径�?
此函数还有其他可选参数，一般不必指�?
### win.regReader("HKEY\_CURRENT\_USER")

仅仅以只读模式打开存在的注册表路径,如果不存在返回null

此函数显式指定只读权限速度较快

### win.regReader()

[返回对象:winRegObject](#winRegObject)

### win.regReaderWow64("HKEY\_LOCAL\_MACHINE")

�?4位系统中访问64位注册表,

32位系统作用与 win.regReader 相同,

仅仅以只读模式打开存在的注册表路径,如果不存在返回nulll

此函数显式指定只读权限速度较快

### win.regReaderWow64()

[返回对象:winRegObject](#winRegObject)

### win.regWow32("HKEY\_LOCAL\_MACHINE")

打开已存在或创建新的注册表路�?

�?4位系统中访问32位注册表,

32位系统下作用�?win.reg 相同

### win.regWow32("HKEY\_LOCAL\_MACHINE",true)

仅仅打开存在的注册表路径,

�?4位系统中访问32位注册表,

32位系统下作用�?win.reg 相同,

如果不存在返回null

### win.regWow32()

[返回对象:winRegObject](#winRegObject)

### win.regWow64("HKEY\_LOCAL\_MACHINE")

打开已存在或创建新的注册表路�?

�?4位系统中访问64位注册表,

32位系统下作用�?win.reg 相同

### win.regWow64("HKEY\_LOCAL\_MACHINE",true)

仅仅打开存在的注册表路径,

�?4位系统中访问64位注册表,

32位系统下作用�?win.reg 相同,

如果不存在返回null

### win.regWow64()

[返回对象:winRegObject](#winRegObject)

## win.reg 成员列表

注册表操�?
打开或创建注册表路径

### win.reg.overrideClasses(runas,proc)

```aardio aardio
win.reg.overrideClasses(false,
    function(){
        /*重定向HKEY_CLASSES_ROOT到HKEY_CURRENT_USER\Software\Classes*/
    }
)

```

### win.reg.overridePredefinedKey("根键","重定向键",回调函数)

```aardio aardio
win.reg.overridePredefinedKey("HKEY_CLASSES_ROOT","HKEY_CURRENT_USER\Software\Classes",
    function(){
        /*注册表已成功重定�?/
    }
);

```

### win.reg.query

直接读取注册表路径的指定�?
### win.reg.query(path,valueName)

返回 @path 参数指定的注册表路径�?
@valueName 指定名字的�?失败返回 null

### win.reg.queryWow64

直接读取注册表路径的指定�?

�?4位系统访�?4位注册表,兼容 32 位系�?
### win.reg.queryWow64(path,valueName)

返回 @path 参数指定的注册表路径�?
@valueName 指定名字的�?失败返回 null

�?4位系统访�?4位注册表,兼容 32 位系�?
## winRegObject 成员列表

### winRegObject.close()

关闭注册表对�?
### winRegObject.delKey("字符串参�?)

删除不包含子项的�?
### winRegObject.delKeyTree("字符串参�?)

删除包含子项的键,

请慎用以避免删除重要的注册表�?
### winRegObject.delValue("字符串参�?)

删除值，

参数 @1 指定值名称（null �?空串表示默认值）�?
### winRegObject.eachKey

```aardio aardio
for(name,writeTime in reg.eachKey() ){
    var subKey = reg.open(name);
    /*name 为子键名,
writeTime �?::FILETIME 结构�?
可用 fsys.time 解析*/
    subKey.close()
}

```

### winRegObject.eachValue

```aardio aardio
for(name,value,t in reg.eachValue()) {

}

```

### winRegObject.enumKey

```aardio aardio
winRegObject.enumKey(

    function(
        subKey, /*这是某个子节�?win.reg对象)*/
        keyname/*这是reg子节点的一个子项的名字*/
    ){
        if( subKey.delKey(keyname)  )
            io.print("删除" + keyname + "成功")
    }
)

```

### winRegObject.keys()

获取所有子键的键名

### winRegObject.load("/backup")

从文件导入到注册�?
### winRegObject.open("字符串参�?)

打开已存在或创建新的子路�?

返回新的win.reg对象,

### winRegObject.open("字符串参�?,true)

仅仅打开已存在的子路�?

返回新的win.reg对象,

如果不存在返回null

### winRegObject.open()

[返回对象:winRegObject](#winRegObject)

### winRegObject.path

注册表路�?
### winRegObject.queryTable(names,...)

遍历当前注册表项的所有子�?

获取 @names 指定名称的所有�?

@names 可以是名称数�?也可以是多个字符串参�?

返回值是�?表的键为子项名称，值为包含各子项名值对的表,

如果子项第一个值名称对应的值为 null 则忽略该�?

失败返回 null

### winRegObject.queryValue("字符串参�?)

查询值，

参数 @1 指定值名称（null �?空串表示默认值）�?
成功返回�?为查询到的数据值，返回�?为一个表示值类型的数值，

自动识别类型:

REG\_SZ,REG\_EXPAND\_SZ 类型返回字符�?

REG\_EXPAND\_SZ 字符串可�?string.expand 函数展开,

REG\_MULTE\_SZ 类型返回字符串数组，

REG\_BINARY类型返回buffer对象,REG\_DWORD类型返回数值，

REG\_QWORD类型返回math.size64对象表示�?4位无符号长整数，

REG\_DWORD，REG\_DWORD\_BIG\_ENDIAN类型返回数�?
### winRegObject.queryValueTable

返回表，包含当前键的指定名值对

### winRegObject.queryValueTable()

返回表，包含当前键的所有名值对

### winRegObject.queryValueTable(default)

参数 @default 指定默认�?
在参�?@1 中填入当前键的所有名值对

返回参数 @1

### winRegObject.queryValueTable(names,...)

返回表，包含当前键的指定名值对

@names 参数可以是一个要查询的值名称数�?

也可以是用于指定查询值名称的一个或多个字符串参�?

第一个值名称指定的值为 null 则返�?null,

### winRegObject.renameKey("字符串参�?)

重命名当前打开的键

参数只要写新的键名就可以,不要在参数中写包含反斜杠的注册表路径

### winRegObject.save("/backup")

导出注册表到文件

### winRegObject.setBinValue(name,vlaue)

设置二进制值，

参数 @1 指定值名称（null �?空串表示默认值）�?
参数 @2 指定要存储的�?
### winRegObject.setDwValue(name,vlaue)

设置32位数�?

参数 @1 指定值名称（null �?空串表示默认值）�?
参数 @2 指定要存储的�?
### winRegObject.setDwValueBigEndian(name,vlaue)

设置大端�?32 位数值，

参数 @1 指定值名称（null �?空串表示默认值）�?
参数 @2 指定要存储的�?
### winRegObject.setExpandValue(name,vlaue)

设置含环境变量的字符串�?

参数 @1 指定值名称（null �?空串表示默认值）�?
参数 @2 指定要存储的�?
### winRegObject.setMultiSzValue(name,vlaue)

设置复合字符串值，

参数 @1 指定值名称（null �?空串表示默认值）�?
参数 @2 可用字符串数组指定要存储的值，

也可以用多个参数传递多个字符串�?
### winRegObject.setQwValue(name,vlaue)

设置64位数�?

参数 @1 指定值名称（null �?空串表示默认值）�?
参数 @2 支持 math.size64 对象表示�?64 位长整数或普通数�?
### winRegObject.setSzValue(name,vlaue)

设置字符串�?

参数 @1 指定值名称（null �?空串表示默认值）�?
参数 @2 指定要存储的�?
### winRegObject.setValue(name,vlaue)

设置注册表值，自动设置类型�?
参数 @1 指定值名称（null �?空串表示默认值）�?
参数 @2 指定要存储的�?
### 自动完成常量

\_REG\_BINARY=3

\_REG\_CREATED\_NEW\_KEY=1

\_REG\_DWORD=4

\_REG\_DWORD\_BIG\_ENDIAN=5

\_REG\_DWORD\_LITTLE\_ENDIAN=4

\_REG\_EXPAND\_SZ=2

\_REG\_FULL\_RESOURCE\_DESCRIPTOR=9

\_REG\_LINK=6

\_REG\_MULTI\_SZ=7

\_REG\_NONE=0

\_REG\_NOTIFY\_CHANGE\_ATTRIBUTES=2

\_REG\_NOTIFY\_CHANGE\_LAST\_SET=4

\_REG\_NOTIFY\_CHANGE\_NAME=1

\_REG\_NOTIFY\_CHANGE\_SECURITY=8

\_REG\_OPENED\_EXISTING\_KEY=2

\_REG\_OPTION\_BACKUP\_RESTORE=4

\_REG\_OPTION\_CREATE\_LINK=2

\_REG\_OPTION\_NON\_VOLATILE=0

\_REG\_OPTION\_RESERVED=0

\_REG\_OPTION\_VOLATILE=1

\_REG\_QWORD=0xB

\_REG\_REFRESH\_HIVE=2

\_REG\_RESOURCE\_LIST=8

\_REG\_RESOURCE\_REQUIREMENTS\_LIST=0xA

\_REG\_SZ=1

\_REG\_WHOLE\_HIVE\_VOLATILE=1

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/win/reg.md)

