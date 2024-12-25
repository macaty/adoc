[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# sqlite.model 库模块帮助文�?
## sqlite 成员列表

### sqlite.model

SQL 连贯操作（链式操作）�?
一般不建议使用这种方式�?
### sqlite.model()

参数中请指定 sqlite 连接对象

[返回对象:sqliteModelObject](#sqliteModelObject)

## sqliteModelObject 成员列表

### sqliteModelObject.and()

指定 AND 查询条件,

参数必须是指定一个或多个键值对的表（以 AND 组合条件�?
[返回对象:sqliteModelObject](#sqliteModelObject)

### sqliteModelObject.asc()

查询结果升序排列

[返回对象:sqliteModelObject](#sqliteModelObject)

### sqliteModelObject.clone()

复制对象

[返回对象:sqliteModelObject](#sqliteModelObject)

### sqliteModelObject.create()

生成创建表的 SQL

生成查询表的 SQL

[返回对象:sqliteModelObject](#sqliteModelObject)

[返回对象:sqliteModelObject](#sqliteModelObject)

### sqliteModelObject.delete()

生成查询表的 SQL

[返回对象:sqliteModelObject](#sqliteModelObject)

### sqliteModelObject.desc()

查询结果降序排列

[返回对象:sqliteModelObject](#sqliteModelObject)

### sqliteModelObject.each

```aardio aardio
for 字段�?字段�? in sqliteModelObject.each() {
    io.print( 字段�?字段�? )
}

```

### sqliteModelObject.enum(sql)

```aardio aardio
sqliteModelObject.enum( function(tname,tvalue){
        for(i=1;#tname;1){
            io.print(tname[i],tvalue[i])
        }

    }
)

```

### sqliteModelObject.exec()

执行sql语句,

如果指定多个参数则调�?string.format 格式化参数一生成 SQL 语句,

如果参数 @1 �?table 对象,则格式化所�?@前缀的命名参数并生成 SQL 语句

出错则抛出异�?

### sqliteModelObject.fields()

指定字段�?可以是多个参�?也可以是一个数�?

参数也可以是用逗号分隔字段名的字符�?
[返回对象:sqliteModelObject](#sqliteModelObject)

### sqliteModelObject.getFiledsNames()

返回表的字段名数�?
### sqliteModelObject.getTable()

[返回对象:sqliteModelObject](#sqliteModelObject)

### sqliteModelObject.insert()

生成插入表的 SQL

生成插入表的 SQL

参数中可以用一个表指定要插入的�?
参数如果是一个窗体对�?自动获取同名控件中的值作为对应的插入�?
[返回对象:sqliteModelObject](#sqliteModelObject)

### sqliteModelObject.limit

限制反回的查询记录数

### sqliteModelObject.limit()

[返回对象:sqliteModelObject](#sqliteModelObject)

### sqliteModelObject.limit(limit,offset)

参数@1限定返回的记录数,可选用参数@2指定开始位�?
### sqliteModelObject.or()

指定 OR 查询条件,

参数必须是指定一个或多个键值对的表（表内字段仍�?AND 组合条件�?
[返回对象:sqliteModelObject](#sqliteModelObject)

### sqliteModelObject.orderBy()

指定排序字段�?可以是多个参�?也可以是一个数�?

参数也可以是用逗号分隔字段名的字符�?
[返回对象:sqliteModelObject](#sqliteModelObject)

### sqliteModelObject.prepare()

编译SQL预处理命�?

1. 如果参数@1为table对象将参数@1转换为WHERE条件语句

2. 否则调用 string.format 格式化sql语句


   可选参�?@1 指定查询条件（table对象或字符串�?


   可选增加任意个附加 SQL 参数

[返回对象:sqliteStmtObject](#sqliteStmtObject)

### sqliteModelObject.primary()

指定主键字段�?可以是多个参�?也可以是一个数�?

参数也可以是用逗号分隔字段名的字符�?
[返回对象:sqliteModelObject](#sqliteModelObject)

### sqliteModelObject.sql

字符串属性，存放生成�?SQL 语句�?
或者把对象传入 tostring 也可以返回此属性�?
### sqliteModelObject.stepQuery()

查询并返回首行数�?失败返回null,状态码.

如果sql中包�?@"字符,即可使用参数@1指定的table对象自动绑定命名参数

### sqliteModelObject.table()

指定表名

[返回对象:sqliteModelObject](#sqliteModelObject)

### sqliteModelObject.update()

生成更新表的 SQL�?
参数必须是指定一个或多个键值对的表

[返回对象:sqliteModelObject](#sqliteModelObject)

### sqliteModelObject.where()

指定查询条件,

参数必须是指定一个或多个键值对的表（以 AND 组合条件�?
[返回对象:sqliteModelObject](#sqliteModelObject)

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/sqlite/model.md)

