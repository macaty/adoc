[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# sqlite.base 库模块帮助文�?
## sqlite 成员列表

SQLite（嵌入式数据库）支持�?
此支持库使用�?SQLite 组件体积较小，但并非最新版�?
功能一般够用，但不支持一�?SQLite 新版才有的特性�?
如果�?sqlite 导入语句替换�?sqlite.latest 扩展库导入语句，

则会改用新版 SQLite 组件，体积会大一些，但支持的功能更多一些�?
其他代码中的 sqlite 不需要替换为 sqlite.latest

如果需要自定义 SQLite 版本，请参�?sqlite.latest 扩展库源�?
### sqlite(":memory:")

创建内存数据�?
### sqlite("\\数据库路�?)

参数一指定数据库路�?支持自动创建数据库文�?

第二个参�?可选参�?指定数据库密�?sqlite.aes128或sqlite.aes256支持该参�?

第三个参�?可选参�?使用一个或多个\_SQLITE\_OPEN\_前缀常量指定连接选项

默认启用多线程模�?多线程共用单个数据连接不安全,否则就是安全�?
多线程模式可并发�?但不可同时写�?
### sqlite("file:数据库路�?

使用 URI 指定数据库路径与参数�?
参数@2 可选用表指�?URI 参数，或用字符串指定密钥�?
也可以在参数 @1 �?URI 后面直接写参数�?
文档 [https://www.sqlite.org/uri.html](https://www.sqlite.org/uri.html)

### sqlite()

[返回对象:sqliteConnObject](#sqliteConnObject)

### sqlite.ABORT

4 //回调函数请求中止

### sqlite.AUTH

23 //认证禁止

### sqlite.BUSY

5 //数据库文件被锁定

### sqlite.CANTOPEN

14 //不能打开数据库文�?
### sqlite.CONSTRAINT

19 //因约束违背而中�?
### sqlite.CORRUPT

11 //数据库文件变�?
### sqlite.DONE

101 //sqlite3\_step()完成执行,已无数据

### sqlite.EMPTY

16 //数据库是空的

### sqlite.ERROR

1 //SQL错误或数据库不存�?
### sqlite.FORMAT

24 //附属数据库格式错�?
### sqlite.FULL

13 //插入失败因为数据库满

### sqlite.INTERNAL

2 //SQLite内部逻辑错误(没有使用)

### sqlite.INTERRUPT

9 //操作被sqlie3\_interrupt()中止

### sqlite.IOERR

10 //磁盘I=O错误

### sqlite.LOCKED

6 //数据库中的一表被锁定

### sqlite.MISMATCH

20 //数据类型不匹�?
### sqlite.MISUSE

21 //库使用方法不�?
### sqlite.NOLFS

22 //主机不支持库中操作系统功�?
### sqlite.NOMEM

7 //malloc()分配堆失�?
### sqlite.NOTADB

26 //打开非数据库文件

### sqlite.NOTFOUND

12 //表或纪录没有找到(没有使用)

### sqlite.OK

0 //成功执行

### sqlite.PERM

3 //访问许可禁止

### sqlite.PROTOCOL

15 //数据库锁协议错误

### sqlite.RANGE

25 //sqlite3\_bind()�?个参数超出范�?
### sqlite.READONLY

8 //企图写只读数据库

### sqlite.ROW

100 //sqlite3\_step()有另一行数据就�?
### sqlite.SCHEMA

17 //数据库模式改�?
### sqlite.TOOBIG

18 //单行数据过多(没有使用)

### sqlite.\_dll

[返回对象:dllModuleObject](../raw/_.html#dllModuleObject)

### sqlite.aes128

支持AES128位数据加密版本sqlite支持�?
### sqlite.aes128("\\数据库路�?)

参数一指定数据库路�?支持自动创建数据库文�?

第二个参�?可选参�?指定数据库密�?sqlite.aes128或sqlite.aes256支持该参�?

### sqlite.aes128()

[返回对象:sqliteConnObject](#sqliteConnObject)

### sqlite.aes256

支持AES256位数据加密版本sqlite支持�?
### sqlite.aes256("\\数据库路�?)

参数一指定数据库路�?支持自动创建数据库文�?

第二个参�?可选参�?指定数据库密�?sqlite.aes128或sqlite.aes256支持该参�?

### sqlite.aes256()

[返回对象:sqliteConnObject](#sqliteConnObject)

### sqlite.assertf(/\*调用sqlite API函数\*/)

第一个参数是API返回的状态�?
如果发生错误则抛出异常终断程�?并显示错误信�?
### sqlite.busy\_handler

```aardio aardio
dll.api("sqlite3_busy_handler","int(POINTER pDB,pointer handle,pointer)");

```

### sqlite.busy\_timeout

```aardio aardio
dll.api("sqlite3_busy_timeout","int(POINTER pDB,int ms)");

```

### sqlite.changes

```aardio aardio
dll.api("sqlite3_changes","int(pointer db)");

```

### sqlite.checkResult(failed,err,level)

参数一: sqlite API的第一个返回�?
参数�?可选参�?:sqlite返回的错误信息指�?
参数�?可选参�?: 抛出异常的调用级�?2为调用checkResult的函�?3为调用当前函数的函数

### sqlite.close

```aardio aardio
dll.api("sqlite3_close","int(pointer db)");

```

### sqlite.escape()

转义参数指定值为用于 SQL 查询语句的参数化�?
### sqlite.escapeId()

如果传入参数是文本则转换�?SQL 标识�?

返回文本首尾会添加反引号,

如果传入参数是表, 则格式化�?SQL 键值对并以 AND 为分隔符,

如果表中的值为数组,则格式化�?IN 语句

### sqlite.exec

```aardio aardio
dll.api("sqlite3_exec","int(POINTER db,STRING sql,pointer callback,pointer callback_arg,pointer &)");

```

### sqlite.finalize

```aardio aardio
dll.api("sqlite3_finalize","int(POINTER stmt)");

```

### sqlite.format(SQL语句,格式化参�?..)

格式�?SQL 查询语句�?
所有需要格式化 SQL 语句的函数调用此函数格式�?SQL语句,

如果格式化参数不是表则调�?string.format格式�?否则按以下规则格式化:

SQL语句�?�??占位符使用表的数组元素格式化,

@字符开始的命名参数使用表的名值对元素格式�?

其中??格式化为标识�?其他占位符格式化为参数值�?
字符串转为SQL安全转义字符�?buffer转为X'4D7953514C'格式,

数组则自动展开为列�?例如{'a', 'b'}格式化为'a', 'b'

嵌套数组则格式化为分组列�?例如{{'a', 'b'}, {'c', 'd'}} 格式化为 ('a', 'b'), ('c', 'd')

非数组的命名表，则格式化�?SQL 键值对,默认以逗号为分隔符,

??占位符格式化 SQL 键值对则以 AND 为分隔符,并将数组值转换为IN语句

### sqlite.last\_insert\_rowid

```aardio aardio
dll.api("sqlite3_last_insert_rowid","int(pointer db)");

```

### sqlite.lasterr(db,errcode)

参数1:指定数据库连接句�?

参数2:可选使用此参数指定错误代码,

返回最后一次发生错误的错误信息,以及错误代码.

### sqlite.prepare

```aardio aardio
dll.api("sqlite3_prepare","int(POINTER db,string szSql,int nByte,pointer &stmt,pointer& pzTail)");

```

### sqlite.prepare2

```aardio aardio
dll.api("sqlite3_prepare_v2","int(POINTER db,string szSql,int nByte,pointer &stmt,pointer& pzTail)");

```

### sqlite.reset

```aardio aardio
dll.api("sqlite3_reset","int(POINTER stmt)");

```

### sqlite.step

```aardio aardio
dll.api("sqlite3_step","int(POINTER stmt)");

```

### sqlite.time(表示时间的字符串或数�?

参数可以是时间数值、时间字符串、或其他datetime对象

返回time对象,默认使用格式化串"%Y-%m-%d %H:%M:%S"

### sqlite.version()

返回版本号数�?以及文本�?
### sqlite.wal\_checkpoint

```aardio aardio
dll.api("sqlite3_wal_checkpoint","int(POINTER pDB,pointer zDb)");

```

## sqlite.bind 成员列表

### sqlite.bind. blob

```aardio aardio
dll.api("sqlite3_bind_blob","int(pointer stmt, int, pointer, int n, pointer )");

```

### sqlite.bind.clear

```aardio aardio
dll.api("sqlite3_clear_bindings","int(pointer stmt)");

```

### sqlite.bind.double

```aardio aardio
dll.api("sqlite3_bind_double","int(pointer stmt, int, double)");

```

### sqlite.bind.int

```aardio aardio
dll.api("sqlite3_bind_int","int(pointer stmt, int, int)");

```

### sqlite.bind.long64

```aardio aardio
dll.sqlite3_bind_int64;

```

### sqlite.bind.parameter\_index

```aardio aardio
dll.api("sqlite3_bind_parameter_index","int(pointer stmt, string zName)");

```

### sqlite.bind.text

```aardio aardio
dll.api("sqlite3_bind_text","int(pointer stmt, int, string, int n,pointer )");

```

### sqlite.bind.text16

```aardio aardio
dll.api("sqlite3_bind_text16","int(pointer stmt, int,ustring, int, pointer )");

```

### sqlite.bind.value

```aardio aardio
dll.api("sqlite3_bind_value","int(pointer stmt, int, pointer)");

```

### sqlite.bind.zeroblob

```aardio aardio
dll.api("sqlite3_bind_zeroblob","int(pointer stmt, int, int n)");

```

## sqlite.bind.bind 成员列表

### sqlite.bind.bind.null

```aardio aardio
dll.api("sqlite3_bind_null","int(pointer stmt, int)");

```

## sqlite.column 成员列表

### sqlite.column. \_blob

```aardio aardio
dll.api("sqlite3_column_blob","pointer(POINTER stmt, int iCol)");

```

### sqlite.column.blob(stmt,iCol)

读取二进制数�?并返回buffer类型字节数组,

如果存储的是一个序列化后的table对象,则返回table对象.

### sqlite.column.bytes

```aardio aardio
dll.api("sqlite3_column_bytes","int(POINTER stmt, int iCol)");

```

### sqlite.column.bytes16

```aardio aardio
dll.api("sqlite3_column_bytes16","int(POINTER stmt, int iCol)");

```

### sqlite.column.count

```aardio aardio
dll.api("sqlite3_column_count","int(POINTER stmt)");

```

### sqlite.column.double

```aardio aardio
dll.api("sqlite3_column_double","double(POINTER stmt, int iCol)");

```

### sqlite.column.int

```aardio aardio
dll.api("sqlite3_column_int64","long(POINTER stmt, int iCol)");

```

### sqlite.column.name(stmt,iCol)

返回字段�?
### sqlite.column.queryValue(iCol)

返回指定列的数据,自动识别数据类型

### sqlite.column.text(stmt,iCol)

返回文本,自动由UTF8转换为ANSI

### sqlite.column.text16

```aardio aardio
dll.api("sqlite3_column_text16","pointer(POINTER stmt, int iCol)");

```

### sqlite.column.type(stmt,iCol)

返回类型ID,以及类型�?
### sqlite.column.typeName\[类型ID\]

根据类型ID,返回类型�?
### sqlite.column.value

```aardio aardio
dll.api("sqlite3_column_value","int(POINTER stmt, int iCol)");

```

## sqlite.formatResult 成员列表

### sqlite.formatResult.(failed,err)

参数一: sqlite API的第一个返回�?
参数�?可选参�?:sqlite返回的错误信息指�?
对于原始Sqlite API返回的err指针,必须调用此函数转换为字符串并释放该指�?
## sqlite.table 成员列表

### sqlite.table. get

```aardio aardio
dll.api("sqlite3_get_table","int(POINTER db,string zSql,pointer &pazResult,int &pnRow,int &pnColumn,pointer &errmsg)");

```

### sqlite.table.free

```aardio aardio
dll.api("sqlite3_free_table","int(pointer azResult)")

```

## sqliteConnObject 成员列表

### sqliteConnObject.beginTrans("EXCLUSIVE")

开始事�?
尝试获取EXCLUSIVE�?保证没有其他连接)

### sqliteConnObject.beginTrans("IMMEDIATE")

开始事�?
尝试获取RESERVED�?其他连接可读)

### sqliteConnObject.beginTrans()

开始DEFERRED事务

默认不获取任何锁,直到需要锁的时候才获取�?

开启事务以�?可使用rollbackTrans()函数撤消所有更�?

使用commitTrans()函数提交所有更�?

使用此函数可以避免sqlite为每个操作创建一个默认事�?
批量操作数据库时可显著提升sqlite执行效率.

### sqliteConnObject.busyHandler

```aardio aardio
sqliteConnObject.busyHandler(
    function(strBack,count) {
        sleep(1);
        return count < 1000; /*重试次数*/
    },strBack
)

```

### sqliteConnObject.busyTimeout(10000)

数据锁定冲突时的重试时间,以毫秒为单位,成功返回true

busyHandler()函数控制重试次数,busyTimeout()函数控制重试时间

这两个函数可相互影响,设置一个必然然取消另一�?
### sqliteConnObject.changes()

返回数据库最近一次运行exec()所改变的行�?
### sqliteConnObject.close()

关闭数据库连�?
在线程结束时,此函数也会自动调�?
### sqliteConnObject.commitTrans()

提交事务

### sqliteConnObject.config

配置数据库�?
�?sqlite.ciphers �?sqlite 增强扩展库支持此函数�?
用法参考相关扩展库文档�?
### sqliteConnObject.config(name,value)

配置数据库�?
成功返回当前配置值，失败返回 -1�?
@name 指定要修改的配置名，也可以指定包含多个配置名值对的表�?
@value 指定配置值，不指定值则用返回当前值�?
### sqliteConnObject.configCipher

配置加密算法参数�?
�?sqlite.ciphers �?sqlite 增强扩展库支持此函数�?
用法参考相关扩展库文档�?
### sqliteConnObject.configCipher(cipherName,name,value)

配置加密算法参数�?
成功返回当前配置值，失败返回 -1�?
@cipherName 指定加密算法名称�?
### sqliteConnObject.db

当前打开的数据库连接对象

### sqliteConnObject.each

```aardio aardio
for 字段�?字段�? in sqliteConnObject.each("SELECT * from [表名] ORDER BY 排序字段 DESC LIMIT 长度 OFFSET 开始位�?) {
    io.print( 字段�?字段�? )
}

```

### sqliteConnObject.each\_sqlite\_master

```aardio aardio
for Type,name,tbl_name,rootpage,sql in sqliteConnObject.each("SELECT * from [sqlite_master]") {
    io.print( Type,name,tbl_name,rootpage,sql )
}

```

### sqliteConnObject.enum(sql,格式化参�?..)

```aardio aardio
sqliteConnObject.enum(sql,格式化参�?..enum(
    /*sql*/,
    function(tname,tvalue){
        for(i=1;#tname;1){
            io.print(tname[i],tvalue[i])
        }

    }
)

```

### sqliteConnObject.exec("字符串参�?)

执行SQL 语句,出错则抛出异�?

可选增加一个或多个格式化参�?

格式化规则请参�?sqlite.format 函数说明,

格式化参数可以是一个表参数,用于替换SQL中占位符指定的参�?

SQL语句用@�?前缀标明的命名参数使用表的名值对成员格式�?

SQL语句中的?�??占位符使用参数表的数组成员格式化,??用于标识符或WHERE条件�?
### sqliteConnObject.exec\_create\_index

```aardio aardio
sqliteConnObject.exec("CREATE INDEX 索引名字 ON 表名�?索引字段名字)")
//建立索引可加快该字段查询速度.

```

### sqliteConnObject.exec\_create\_table

```aardio aardio
sqliteConnObject.exec("CREATE TABLE 表名(
    ID INTEGER PRIMARY KEY AUTOINCREMENT,
    数值字段名 INTEGER,
    浮点字段�?REAL,
    文本字段�?TEXT,
    二进制字段名 BLOB,
    非空字段�?NOT NULL DEFAULT '默认�?,
    动态类型字段名,
    UNIQUE (ID)
    );"
)

```

### sqliteConnObject.exec\_delete\_sequence

```aardio aardio
sqliteConnObject.exec("DELETE FROM sqlite_sequence WHERE name = '表名'")
//自增ID�?

```

### sqliteConnObject.exec\_delete\_table

```aardio aardio
sqliteConnObject.exec("DELETE FROM 表名 ")
//清空�?
```

### sqliteConnObject.exec\_drop\_table

```aardio aardio
sqliteConnObject.exec("DROP table 表名 ")
//删除�?
```

### sqliteConnObject.exec\_free\_memory

```aardio aardio
sqliteConnObject.exec("VACUUM")//DELETE表后必须调用此语句才能释放空�?
```

### sqliteConnObject.exec\_insert

```aardio aardio
sqliteConnObject.exec("INSERT INTO 表名(字段�? VALUES( �?)")
//插入数据到表�?
```

### sqliteConnObject.exec\_insert\_where\_not\_exists

```aardio aardio
sqliteConnObject.exec("INSERT INTO 表名(字段�? SELECT '插入�? WHERE NOT EXISTS(SELECT * from 表名 WHERE 条件字段�?查询�?;")
//如果符合条件的数据不存在则插入新的数�?
```

### sqliteConnObject.exec\_journal\_mode\_delete

```aardio aardio
sqliteConnObject.exec("journal_mode=DELETE;")

```

### sqliteConnObject.exec\_journal\_mode\_wal

```aardio aardio
sqliteConnObject.exec("PRAGMA journal_mode=WAL;")

```

### sqliteConnObject.exec\_replace

```aardio aardio
sqliteConnObject.exec("REPLACE INTO [表名] (字段�? 字段�?) VALUES (�? �?)")
//如果该表有一个主�?那么当主键值相等的时�?该行数据不存在执行插�?存在则执行更新操�?
```

### sqliteConnObject.exec\_update

```aardio aardio
sqliteConnObject.exec("UPDATE 表名 SET 更新字段 = '更新�? WHERE 条件字段 = 条件�?");

```

### sqliteConnObject.existsTable("字符串参�?)

判断指定的表是否存在

### sqliteConnObject.getTable("SELECT \* FROM \[表名\] /\*SQL 语句\*/")

返回包含行记录组成的table数组对象,

每行是由列名、值组成的table表对象�?
参数@2为可选参�?

如果SQL内使用@前缀指定了命名参�?则参数@2使用 table 指定参数的�?
并且SQL语句中的?�??占位符将使用 sqlite.format 函数格式化为参数@2对应的�?

否则调用sqlite.format格式�??占位符为参数@2指定的�?

如果参数@2不是表，则调�?string.format 使用参数@2开始的所有参数格式化sql

### sqliteConnObject.key("字符串参�?)

输入并验证数据库密钥

成功返回true,失败返回false,错误信息,错误代码

该函数需要使用支持加密的DLL组件重新编译sqlite�?
### sqliteConnObject.lastInsertRowid()

获取最后一次插入操作添加记录的ID

作用类似MSSQL的@@IDENTITY

### sqliteConnObject.lasterr()

返回最后一次发生错误的错误信息,以及错误代码

### sqliteConnObject.prepare("SELECT \* FROM \[表名\] WHERE 字段�?@参数�?)

编译SQL预处理命�?

1、如果参数@2为表对象，参数表中的数组成员用于格式�?SQL 语句中的??占位�?

2、否则调用string.format格式化SQL 语句,

查询SQL示例:

"SELECT \* FROM \[表名\] WHERE 条件字段=12 ORDER BY 排序字段 DESC LIMIT 1 OFFSET 0"

上面SQL语句中LIMIT n OFFSET i 指定第i条记录开始取n条记�?
也可以直接写�?limit i,n

### sqliteConnObject.prepare()

[返回对象:sqliteStmtObject](#sqliteStmtObject)

### sqliteConnObject.prepare\_insert

```aardio aardio
sqliteConnObject.prepare("INSERT INTO [表名] VALUES (?1,?2,?3,?4);")
//创建插入数据SQL命令对象,问号表示参数,可在问号后指定索�?
```

### sqliteConnObject.prepare\_select\_distinct

```aardio aardio
sqliteConnObject.prepare("SELECT DISTINCT 去重字段 FROM [表名]")

```

### sqliteConnObject.rekey("字符串参�?)

添加、清空、重设数据库密钥

成功返回true,失败返回false,错误信息,错误代码

该函数需要使用支持加密的DLL组件重新编译sqlite�?
### sqliteConnObject.rollbackTrans()

回滚事务,取消所有修�?
### sqliteConnObject.stepQuery("SELECT \* FROM \[表名\] /\*SQL 语句\*/")

查询并返回首行数据（名值对格式�?失败返回null,状态码�?
参数@2为可选参�?

如果参数@2是一个指定了SQL 查询参数值的�?

SQL 中@前缀的命名参数将由数据库绑定同名参数�?这并非调�?sqlite.format 格式�?

SQL语句中的?�??占位符将使用参数@2中的数组值调�?sqlite.format 函数格式�?

如果参数@2不是表，则调�?string.format 使用参数@2开始的所有参数格式化sql

### sqliteConnObject.stepResult("SELECT \* FROM \[表名\] /\*SQL 语句\*/")

查询并返回首行数据（数组格式�?失败返回null,状态码�?
参数@2为可选参�?

如果参数@2是一个指定了SQL 查询参数值的�?

SQL 中@前缀的命名参数将由数据库绑定同名参数�?这并非调�?sqlite.format 格式�?

SQL语句中的?�??占位符将使用参数@2中的数组值调�?sqlite.format 函数格式�?

如果参数@2不是表，则调�?string.format 使用参数@2开始的所有参数格式化sql

### sqliteConnObject.walCheckpoint()

执行checkpoint操作�?WAL日志文件内容被写回数据库文件

## sqliteStmtObject 成员列表

### sqliteStmtObject.bind.blob()

[返回对象:sqliteStmtObject](#sqliteStmtObject)

### sqliteStmtObject.bind.blob(二进制字符串)

绑定一个参�?参数在SQL 语句中用问号表示

可使用第二个参数指定问号的位�?
返回命令对象自身

### sqliteStmtObject.bind.boolean()

将bool值转换为数值存�?
false存为0,true存为1;

### sqliteStmtObject.bind.buffer()

将buffer类型转换为blob类型存储

### sqliteStmtObject.bind.cdata()

将cdata类型转换为blob类型存储

### sqliteStmtObject.bind.clear()

清除所有绑定�?
成功返回0

### sqliteStmtObject.bind.double()

[返回对象:sqliteStmtObject](#sqliteStmtObject)

### sqliteStmtObject.bind.double(浮点数�?

绑定一个参�?参数在SQL 语句中用问号表示

可使用第二个参数指定问号的位�?
返回命令对象自身

### sqliteStmtObject.bind.int()

[返回对象:sqliteStmtObject](#sqliteStmtObject)

### sqliteStmtObject.bind.int(数�?

绑定一个参�?参数在SQL 语句中用问号表示

可使用第二个参数指定问号的位�?
返回命令对象自身

### sqliteStmtObject.bind.long64()

[返回对象:sqliteStmtObject](#sqliteStmtObject)

### sqliteStmtObject.bind.long64(数�?

绑定一�?4位参�?

支持整数值或math.size64对象,参数在SQL 语句中用问号表示

可使用第二个参数指定问号的位�?
返回命令对象自身

### sqliteStmtObject.bind.null()

绑定一个空值参�?参数在SQL 语句中用问号表示

可使用第二个参数指定问号的位�?
返回命令对象自身

[返回对象:sqliteStmtObject](#sqliteStmtObject)

### sqliteStmtObject.bind.number()

如果是整数则调用bind.int()

是浮点数则调用bind.double;

### sqliteStmtObject.bind.parameter

绑定一个动态类型SQL命令参数

### sqliteStmtObject.bind.parameter(参数�?参数索引)

绑定一个命令动态类型SQL命令参数,自动绑定合适的数据类型.

参数2指定索引位置,默认�?

返回命令对象自身

### sqliteStmtObject.bind.parameterAtNames()

[返回对象:sqliteStmtObject](#sqliteStmtObject)

### sqliteStmtObject.bind.parameterAtNames(参数�?

绑定一个表中所有键值对到相应的命名参数,

对所有键名添�?@"字符作为SQL参数�?

返回命令对象自身,以及成功绑定的参数数�?

### sqliteStmtObject.bind.parameterByName()

[返回对象:sqliteStmtObject](#sqliteStmtObject)

### sqliteStmtObject.bind.parameterByName(参数�?"@参数�?)

绑定一个命令动态类型SQL命令参数,自动绑定合适的数据类型.

参数2指定命名参数,参数名可�?@',':','$'等符号作为首字符

### sqliteStmtObject.bind.parameterByNames()

[返回对象:sqliteStmtObject](#sqliteStmtObject)

### sqliteStmtObject.bind.parameterByNames(参数�?

绑定一个表中所有键值对到相应的命名参数,

可使用第二个参数指定'@',':','$'等符号作为参数名前缀,

返回命令对象自身,以及成功绑定的参数数�?

### sqliteStmtObject.bind.parameterIndex("@参数�?)

返回命名参数的索引�?参数名可�?@',':','$'等符号作为首字符,

成功返回索引,如果在SQL 语句中未找到该名字则返回0

### sqliteStmtObject.bind.parameterIndex()

[返回对象:sqliteStmtObject](#sqliteStmtObject)

### sqliteStmtObject.bind.parameters

绑定多个动态类型SQL命令参数

### sqliteStmtObject.bind.parameters()

[返回对象:sqliteStmtObject](#sqliteStmtObject)

### sqliteStmtObject.bind.parameters(任意多个命令参数)

可以用一个数组参数或多个参数指定 SQL 命令参数,

绑定参数时将自动选择合适的数据类型,

参数位置对应SQL 语句中的问号位置

返回命令对象自身

### sqliteStmtObject.bind.string()

存为text类型（UTF8字符串）

### sqliteStmtObject.bind.table(table对象)

如果定义了tostring元方�?则调用并转换为文本存�?

如果是一个时间对�?则使用标准格式转换为文本存储

否则序列化为blob类型存储

### sqliteStmtObject.bind.text()

[返回对象:sqliteStmtObject](#sqliteStmtObject)

### sqliteStmtObject.bind.text(普通文�?

绑定一个参�?参数为普通文�?
转换为UTF8存入数据�?
### sqliteStmtObject.bind.text16()

[返回对象:sqliteStmtObject](#sqliteStmtObject)

### sqliteStmtObject.bind.text16(UTF16编码文本)

绑定一个参�?参数为UTF16文本

### sqliteStmtObject.bind.utf16()

[返回对象:sqliteStmtObject](#sqliteStmtObject)

### sqliteStmtObject.bind.utf16(UTF16编码文本)

绑定一个参�?参数为UTF16文本

### sqliteStmtObject.bind.utf8()

[返回对象:sqliteStmtObject](#sqliteStmtObject)

### sqliteStmtObject.bind.utf8(UTF8编码文本)

绑定一个参�?参数为UTF8文本

该函数不会转换编�?
### sqliteStmtObject.column.count()

返回列数�?
### sqliteStmtObject.column.name(iCol)

返回指定列名�?
### sqliteStmtObject.column.queryValue(iCol)

返回指定列的数据�?
此函数自动识别并转换类型

### sqliteStmtObject.column.type(iCol)

返回指定列字段类�?
### sqliteStmtObject.each

```aardio aardio
for 字段�?字段�? in sqliteStmtObject.each() {
    io.print( 字段�?字段�? )
}

```

### sqliteStmtObject.finalize()

释放预处理命令对�?

应当在不再使用此命令对象时尽早调用此函数�?
如果忘记调用，回收对象时也会自动调用此函�?
### sqliteStmtObject.getColumns()

返回当前查询的列名字数组.

### sqliteStmtObject.getTable()

返回全部数据,

返回值为table数组,每行记录为一个数组元�?

### sqliteStmtObject.prepare("SELECT \* FROM \[表名\] /\*SQL 语句\*/")

重新编译SQL预处理命�?

可选参�?:指定查询条件(table对象或字符串),

可选增加任意个附加sql参数.

### sqliteStmtObject.prepare()

[返回对象:sqliteStmtObject](#sqliteStmtObject)

### sqliteStmtObject.reset()

重置到没有执行之前的状�?已绑定的参数不会变化

执行后需要改变绑定参数时必须首先调用该函�?
### sqliteStmtObject.sql

SQL 指令

### sqliteStmtObject.step(可选输入命名参�?

执行SQL命令并向下移动一�?成功则返回值大于等�?00,

如果提供命令参数�?则自动调�?reset 函数后并自动绑定参数,

参数表可以包含名值对,也可以包含匿名参数值数�?
### sqliteStmtObject.stepQuery()

向后移动一�?并返回当前数�?失败返回null,状态码.

返回table对象,键为列名,值为当前行数�?
### sqliteStmtObject.stepResult()

向后移动一�?并返回当前数�?失败返回null,状态码.

返回数组,键为列序�?值为当前行数�?
### 自动完成常量

\_SQLITE\_OPEN\_AUTOPROXY=0x20

\_SQLITE\_OPEN\_CREATE=4

\_SQLITE\_OPEN\_DELETEONCLOSE=8

\_SQLITE\_OPEN\_EXCLUSIVE=0x10

\_SQLITE\_OPEN\_FULLMUTEX=0x10000

\_SQLITE\_OPEN\_MAIN\_DB=0x100

\_SQLITE\_OPEN\_MAIN\_JOURNAL=0x800

\_SQLITE\_OPEN\_MASTER\_JOURNAL=0x4000

\_SQLITE\_OPEN\_NOMUTEX=0x8000

\_SQLITE\_OPEN\_PRIVATECACHE=0x40000

\_SQLITE\_OPEN\_READONLY=1

\_SQLITE\_OPEN\_READWRITE=2

\_SQLITE\_OPEN\_SHAREDCACHE=0x20000

\_SQLITE\_OPEN\_SUBJOURNAL=0x2000

\_SQLITE\_OPEN\_TEMP\_DB=0x200

\_SQLITE\_OPEN\_TEMP\_JOURNAL=0x1000

\_SQLITE\_OPEN\_TRANSIENT\_DB=0x400

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/sqlite/base.md)

