[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# util.metaProperty 库模块帮助文�?
[关于元表](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/language-reference/datatype/table/meta.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/language-reference/datatype/table/meta.md')

## util 成员列表

### util.metaProperty(properties,...)

```aardio aardio
util.metaProperty(properties,...metaProperty(

    属�?= {
        _get = function(){
            /*读取属性代码写在这�?/
            return null;
        }
        _set = function( value ){
            /*写入属性代码写在这�?/
            ..io.print( owner,value)
        }
    };
)

```

## util.metaProperty 成员列表

用于创建属性元�?

可在构造函数中指定一个或多个初始化参数表,

按参数顺序混入到新创建的属性表并返�?

用返回的属性表作为对象元表,

读写对象中不存在的属性会触发属性元表�?
如果在属性元表中对应属性是一个表,

则读属性会触发属性的get成员函数,写属性会触发该属性的set成员函数�?
否则直接返回属性元表中对应属性的�?
### util.metaProperty.each()

```aardio aardio
for(k,v in util.metaProperty.each(/*对象*/) ){

}

```

### util.metaProperty.extend(类对�?一个或多个混入�?

使用混入表扩展类的属性情

类名字空间必须定义了\_metaProperty静态成�?
并且是一个有效的属性表

### util.metaProperty.is(对象)

对象是否支持metaProperty

### util.metaProperty.isKindOf(对象,类对�?

判断对象是否由指定的类创�?
类必须是使用属性表定义的类,并符合标准规�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/util/metaProperty.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/util/metaProperty.md')

