[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# crypt.des 库模块帮助文�?
## crypt 成员列表

### crypt.des

DES�?DES�?DES 加密算法支持�?
加密模式CBC，填充模式PKCS5（兼�?PKCS7 ），如果与其他编程语言互通要保持一�?
各编程语言兼容的DES兼容写法参考\]( [http://bbs.aardio.com/forum.php?mod=viewthread&tid=13148](javascript:if(confirm('http://bbs.aardio.com/forum.php?mod=viewthread&tid=13148  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ����һ������·���ⲿ������Ϊ������ʼ��ַ�ĵ�ַ��  \n\n�����ڷ������ϴ�����?'))window.location='http://bbs.aardio.com/forum.php?mod=viewthread&tid=13148'))

演示代码�?
```aardio aardio
import crypt.des;

var des = crypt.des();
des.setPassword("abcd12" )

//加密
var sstr = des.encrypt("测试字符�?);

//解密
var str = des.decrypt(sstr);

```

### crypt.des()

返回 DES 加密容器�?
支持 DES�?DES�?DES 加密（根据密钥长度自动选择）�?
可选使用一个字符串参数指定密钥向量（ECB 模式忽略向量）�?
如果要与其他编程语言有相同加解密结果,建议不要设置该参�?
[返回对象:crypy3desObject](#crypy3desObject)

## crypy3desObject 成员列表

### crypy3desObject.allocBuffer

分配加解密需要用到的 buffer�?
### crypy3desObject.allocBuffer(大小,块大�?

分配加解密需要用到的 buffer�?
如果不手动分配，程序将会自动按需分配 buffer�?
参数 @2 可选，可用对象的blockSize属性指定默认块大小�?
### crypy3desObject.blockSize

加密填充的块大小，默认为 8

### crypy3desObject.buffer

加解密时暂存输入输出数据的缓冲区�?
只能通过调用 allocBuffer 函数分配此缓冲区�?
或者由加解密函数自动分配此缓冲区�?
如果未分配缓冲区，或缓冲区大小不够�?
加解密时会重新调�?allocBuffer 函数分配到合适大小�?
一般不应直接访问此属性�?
### crypy3desObject.decrypt

解密数据

### crypy3desObject.decrypt(输入数据,是否已输入全部数�?哈希对象,选项)

参数 @1 指定字符串或 buffer�?
除第一个参数以外，其他参数都是可选参数�?
分块解密时，参数 @2 必须�?flase 且参�?@1 的长度必须是块大小的倍数�?
成功返回解密文本,失败返回�?

可使�?.lasterr()函数获取错误信息

### crypy3desObject.decrypt(输入缓冲�?输入数据大小,哈希对象,选项)

参数 @1 指定 buffer 或字符串�?
如果参数 @2 指定的数值小于缓冲区据总长度，解密结束�?
可使�?-1 表示解密结束，且输入数据大小等于缓冲区大小�?
其他参数可忽略不用管�?
成功返回存放解密结果的缓冲区，返回�?2 为解密长度�?
需要分块解密的算法，例�?RSA 算法返回的解密结果为字符串�?
失败返回 null, 错误信息,错误代码�?
用法可参�?decryptFile 函数源码�?
### crypy3desObject.decryptFile

解密文件

### crypy3desObject.decryptFile(输入文件,输出文件,缓冲区大�?进度回调函数,哈希对象,选项)

参数 @1 指定要解密的文件。参�?@2 指定要保存解密结果的文件�?
文件参数都可以指定文件路径、文件对象（兼容 io.file,fsys.file,fsys.stream）�?
可选用参数 @3 指定分块加密的字节长度，默认�?1MB�?
指定字节长度时会自动调整到对齐块大小，参数不需要考虑对齐�?
可选指定进度回调函数，回调参数 @1,@2 分别为输入文件总长度、已读取长度�?
其他调用参数（哈希对象，选项）一般不必指定�?
函数执行成功返回 true，失败返�?null,错误信息�?
### crypy3desObject.encrypt

加密数据

### crypy3desObject.encrypt(输入数据,是否已输入全部数�?哈希对象,选项)

参数 @1 指定字符串或 buffer�?
除第一个参数以外，其他参数都是可选参数�?
分块加密时，参数 @2 必须�?flase 且参�?@1 的长度必须是块大小的倍数�?
成功返回加密文本,失败返回�?

可使�?.lasterr()函数获取错误信息

### crypy3desObject.encrypt(输入缓冲�?输入数据大小,哈希对象,选项)

参数 @1 指定 buffer 或字符串�?
如果参数 @2 指定的数值小于缓冲区据总长度，加密结束�?
可使�?-1 表示解密结束，且输入数据大小等于缓冲区大小�?
其他参数可忽略不用管�?
成功返回存放加密结果的缓冲区，返回�?2 为解密长度�?
需要分块解密的算法，例�?RSA 算法返回的解密结果为字符串�?
失败返回 null, 错误信息,错误代码�?
用法可参�?encryptFile 函数源码�?
### crypy3desObject.encryptFile

加密文件

### crypy3desObject.encryptFile(输入文件,输出文件,缓冲区大�?进度回调函数,哈希对象,选项)

参数 @1 指定要加密的文件。参�?@2 指定要保存加密结果的文件�?
文件参数都可以指定文件路径、文件对象（兼容 io.file,fsys.file,fsys.stream）�?
可选用参数 @3 指定分块加密的字节长度，默认�?1MB�?
指定字节长度时会自动调整到对齐块大小，参数不需要考虑对齐�?
可选指定进度回调函数，回调参数 @1,@2 分别为输入文件总长度、已读取长度�?
其他调用参数（哈希对象，选项）一般不必指定�?
函数执行成功返回 true，失败返�?null,错误信息�?
### crypy3desObject.hasKey()

检测是否已设置密钥

### crypy3desObject.setInitVector(字符串向�?选项)

设置初始化向量，参数 @2 可选�?
成功返回true�?
ECB 模式忽略向量（IV），不需要指定�?
### crypy3desObject.setKeyParam(类型,数据�?选项)

设置加密参数

数据值可以是结构�?字符串，�?buffer 对象,

如果数据值一个数值参�?则转换为表示32位整型数值地址的结构体指针

成功返回true,失败请使�?..lasterr()获取错误信息

### crypy3desObject.setKeyParamMode(\_CRYPT\_MODE\_ECB)

设置�?ECB 加密模式�?
ECB 模式忽略向量（IV）�?
成功返回 true,失败请使�?..lasterr()获取错误信息

### crypy3desObject.setKeyParamPadding(\_PKCS5)

设置加密填充方式

成功返回true,失败请使�?..lasterr()获取错误信息

### crypy3desObject.setPassword

设置密钥，根据密钥长度自动选择算法�?
如果遇到密钥长度不一致的情况，直接截断就可以�?
例如 DES 最�?8 字节密钥，如果遇�?32 字节密钥一般只�?
调用 string.left 取最前面 8 字节就可以�?
### crypy3desObject.setPassword("密钥",选项)

密钥使用�?0 方式自动对齐�?
密钥长度小于等于 8 字节时使�?DES 加密

密钥长度小于等于 16 字节时使�?2DES 加密

密钥长度小于等于 24 字节时使�?3DES 加密,

超过 24 字节使用使用MD5算法创建转换�?4位密�?

参数 @2 不需要指�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/crypt/des.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/crypt/des.md')

