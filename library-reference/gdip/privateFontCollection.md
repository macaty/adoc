[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# gdip.privateFontCollection 库模块帮助文�?
## gdip 成员列表

### gdip.privateFontCollection()

私有字体集合,调用时不应在参数中指定指�?
较老的系统在私有字体集合释放后,会导致该容器加载并仍在使用的的字体异�?
稳妥的方式是调用 gdip.privateFontCollection.getInstance 函数

获取私有字体集合的单一实例

[返回对象:gdipprvfontcollObject](#gdipprvfontcollObject)

## gdip.privateFontCollection 成员列表

私有字体集合,

请在 fonts 名字空间下添加库,并调�?fonts.createFamily 函数注册嵌入字体

### gdip.privateFontCollection.createFamily(字体路径,字体�?

创建字体家族,创建失败返回空�?
参数@1可以是路径或资源文件、内存数�?
如果不指定名�?则返回字体列表中的第一个字体家�?
### gdip.privateFontCollection.createFont(字体路径,字体�?大小,样式,单位)

创建字体

参数@1可以是路径或资源文件、内存数�?
单位默认为像�?
### gdip.privateFontCollection.getInstance()

获取默认的私有字体集�?

较老的系统在私有字体集合释放后,会导致该容器加载并仍在使用的的字体异�?

稳妥的方式是调用此函数获取单一实例的自定义容器

aardio 会在程序结束前自动释放此容器对象,

但手动调用此对象�?delete 函数将被忽略,

[返回对象:gdipprvfontcollObject](#gdipprvfontcollObject)

## gdipprvfontcollObject 成员列表

### gdipprvfontcollObject.add

添加自字义字�?
### gdipprvfontcollObject.add(字体)

参数可以是字体文�?资源文件

或字体文件加载到内存的数�?
### gdipprvfontcollObject.count()

返回字体列表中包含的字体家族总数,

一个字体家族可以用于创建不同大小、不同样式的同名字体

### gdipprvfontcollObject.createFamily

创建字体家族对象

### gdipprvfontcollObject.createFamily("字体�?)

参数为字体名

如果不指定名�?则返回字体列表中的最后一个添加的字体家族

### gdipprvfontcollObject.createFamily()

[返回对象:gdipfamilyObject](#gdipfamilyObject)

### gdipprvfontcollObject.delete()

删除字体

### gdipprvfontcollObject.getFamilies

返回字体集合中的字体家族数组,

一个字体家族可以用于创建不同大小、不同样式的同名字体

### gdipprvfontcollObject.getFamilies(sought,clone)

返回字体集合中的字体家族数组,所有参数可�?

参数 @sought 指定期望返回的字体家族数�?

不指定则自动获取全部字体家族并返�?clone参数指定是否复制字体家族对象,

如果不复制，在字体列表被删除以后，此函数返回的字体家族也不能再使�?
### gdipprvfontcollObject.getLastFamily()

[返回对象:gdipfamilyObject](#gdipfamilyObject)

### gdipprvfontcollObject.getLastFamily(clone)

返回字体集合中的最后一个添加的字体家族,

可选参�?@sought 指定期望返回的字体家族数�?

不指定则自动获取全部字体家族并返�?clone参数指定是否复制字体家族对象,

如果不复制，在字体列表被删除以后，此函数返回的字体家族也不能再使�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/gdip/privateFontCollection.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/gdip/privateFontCollection.md')

