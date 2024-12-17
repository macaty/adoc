[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# fsys.config 库模块帮助文�?
## fsys 成员列表

### fsys.config

基于 fsys.table 的配置文件对象�?
fsys.config 对象用不以下划线开始的名字获取成员会返�?fsys.table 对象�?
fsys.table 可作为普�?table 对象使用�?
在线程退出时将会同步存储到文件中�?
fsys.table 并非实时读写，而是将配置读入内存�?
所以请不要多对象、多线程、多进程打开同一配置文件�?
这会导致多份不同步的配置写入存储设备时会相互覆盖�?
注意此对象不可跨线程传递�?
多线程可通过 winform 成员函数转发到界面线程操作配置文件即可，

多进程可利用原子窗体、进程互斥体避免冲突

创建 fsys.config 对象�?
fsys.config 对象用不以下划线开始的名字获取成员会返�?fsys.table 对象

### fsys.config()

[返回对象:fsysConfigObject](#fsysConfigObject)

### fsys.config(默认配置目录,备选配置目�?

参数 @1 指定默认目录，省略则默认使用 "/config/" 目录�?
如果默认配置目录不存在，且指定了备选配置目录，

则改用备选配置目录。否则自动创建默认配置目录�?
可用 io.appData 函数指定 %LocalAppData% 目录的子目录�?
使用非下划线开始的名字获取 fsys.config 对象成员时，

返回指向配置目录下同名配置文件的 fsys.table 对象�?
一般只应当在主线程中有一个指向同一配置目录�?fsys.config 对象�?
以避�?fsys.table 指向同一个硬盘文件则保存时会相互覆盖

## fsysConfigObject 成员列表

### fsysConfigObject.?

获取值时指定不以下划线开始的配置表名称，

返回一个可自动序列化到同名配置文件的表对象�?
如果此对象名以下划线开始，则可以正常读写值不会序列化为配置文件�?
否则不能对此对象直接赋值，只能对配置表对象的成员赋值�?
配置表可自动自文件加�?退出线程前自动序列化并存入文件�?
仅序列化以字符串、数值为键的元素�?
仅序列化值为字符串、数值、buffer 以及定义�?\_serialize 元方法的成员�?
循环引用的值转换为 null，序列化时忽略成员函�?
[返回对象:fsysTableObject](table.html#fsysTableObject)

### fsysConfigObject.saveAll()

写入所有成�?fsys.table 对象到配置文�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/fsys/config.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/fsys/config.md')

