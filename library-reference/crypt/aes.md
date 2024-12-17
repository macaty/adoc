[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# crypt.aes 库模块帮助文�?
## crypt 成员列表

### crypt.aes

AES加密算法支持�?默认加密模式 CBC,填充模式PKCS7,

注意PKCS5与PKCS7填充规则一�?PKCS5填充1�?字节,PKCS7填充1�?55字节,

而AES数据块分组为16字节也就�?28�?指定PKCS5实际使用的也是PKCS7,

[各编程语言兼容的AES兼容写法参考](javascript:if(confirm('http://bbs.aardio.com/forum.php?mod=viewthread&tid=13818  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ����һ������·���ⲿ������Ϊ������ʼ��ַ�ĵ�ַ��  \n\n�����ڷ������ϴ�����?'))window.location='http://bbs.aardio.com/forum.php?mod=viewthread&tid=13818')

演示代码:

```aardio aardio
import crypt.aes;
var aes = crypt.aes();

//设置密钥
aes.setPassword("12345678");

//加密
var sstr = aes.encrypt("Test String");

//解密
var str = aes.decrypt(sstr);

```

### crypt.aes()

返回AES加密容器,

可选使用一个字符串参数指定密钥向量

如果要与其他编程语言有相同加解密结果,建议不要设置该参�?
[返回对象:crypyAesObject](#crypyAesObject)

## crypyAesObject 成员列表

### crypyAesObject.allocBuffer

分配加解密需要用到的 buffer�?
### crypyAesObject.allocBuffer(大小,块大�?

分配加解密需要用到的 buffer�?
如果不手动分配，程序将会自动按需分配 buffer�?
参数 @2 可选，可用对象的blockSize属性指定默认块大小�?
### crypyAesObject.blockSize

加密填充的块大小，默认为 16

### crypyAesObject.buffer

加解密时暂存输入输出数据的缓冲区�?
只能通过调用 allocBuffer 函数分配此缓冲区�?
或者由加解密函数自动分配此缓冲区�?
如果未分配缓冲区，或缓冲区大小不够�?
加解密时会重新调�?allocBuffer 函数分配到合适大小�?
一般不应直接访问此属性�?
### crypyAesObject.decrypt

解密数据

### crypyAesObject.decrypt(输入数据,是否已输入全部数�?哈希对象,选项)

参数 @1 指定字符串或 buffer�?
除第一个参数以外，其他参数都是可选参数�?
分块解密时，参数 @2 必须�?flase 且参�?@1 的长度必须是块大小的倍数�?
成功返回解密文本,失败返回�?

可使�?.lasterr()函数获取错误信息

### crypyAesObject.decrypt(输入缓冲�?输入数据大小,哈希对象,选项)

参数 @1 指定 buffer 或字符串�?
如果参数 @2 指定的数值小于缓冲区据总长度，解密结束�?
可使�?-1 表示解密结束，且输入数据大小等于缓冲区大小�?
其他参数可忽略不用管�?
成功返回存放解密结果的缓冲区，返回�?2 为解密长度�?
需要分块解密的算法，例�?RSA 算法返回的解密结果为字符串�?
失败返回 null, 错误信息,错误代码�?
用法可参�?decryptFile 函数源码�?
### crypyAesObject.decryptFile

解密文件

### crypyAesObject.decryptFile(输入文件,输出文件,缓冲区大�?进度回调函数,哈希对象,选项)

参数 @1 指定要解密的文件。参�?@2 指定要保存解密结果的文件�?
文件参数都可以指定文件路径、文件对象（兼容 io.file,fsys.file,fsys.stream）�?
可选用参数 @3 指定分块加密的字节长度，默认�?1MB�?
指定字节长度时会自动调整到对齐块大小，参数不需要考虑对齐�?
可选指定进度回调函数，回调参数 @1,@2 分别为输入文件总长度、已读取长度�?
其他调用参数（哈希对象，选项）一般不必指定�?
函数执行成功返回 true，失败返�?null,错误信息�?
### crypyAesObject.encrypt

加密数据

### crypyAesObject.encrypt(输入数据,是否已输入全部数�?哈希对象,选项)

参数 @1 指定字符串或 buffer�?
除第一个参数以外，其他参数都是可选参数�?
分块加密时，参数 @2 必须�?flase 且参�?@1 的长度必须是块大小的倍数�?
成功返回加密文本,失败返回�?

可使�?.lasterr()函数获取错误信息

### crypyAesObject.encrypt(输入缓冲�?输入数据大小,哈希对象,选项)

参数 @1 指定 buffer 或字符串�?
如果参数 @2 指定的数值小于缓冲区据总长度，加密结束�?
可使�?-1 表示解密结束，且输入数据大小等于缓冲区大小�?
其他参数可忽略不用管�?
成功返回存放加密结果的缓冲区，返回�?2 为解密长度�?
需要分块解密的算法，例�?RSA 算法返回的解密结果为字符串�?
失败返回 null, 错误信息,错误代码�?
用法可参�?encryptFile 函数源码�?
### crypyAesObject.encryptFile

加密文件

### crypyAesObject.encryptFile(输入文件,输出文件,缓冲区大�?进度回调函数,哈希对象,选项)

参数 @1 指定要加密的文件。参�?@2 指定要保存加密结果的文件�?
文件参数都可以指定文件路径、文件对象（兼容 io.file,fsys.file,fsys.stream）�?
可选用参数 @3 指定分块加密的字节长度，默认�?1MB�?
指定字节长度时会自动调整到对齐块大小，参数不需要考虑对齐�?
可选指定进度回调函数，回调参数 @1,@2 分别为输入文件总长度、已读取长度�?
其他调用参数（哈希对象，选项）一般不必指定�?
函数执行成功返回 true，失败返�?null,错误信息�?
### crypyAesObject.hasKey()

检测是否已设置密钥

### crypyAesObject.setInitVector(字符串向�?选项)

设置初始化向�?成功返回true,

参数2可�?
### crypyAesObject.setKeyParam(类型,数据�?选项)

设置加密参数

数据值可以是结构�?字符串，�?buffer 对象�?
如果数据值一个数值参�?则转换为表示32位整型数值地址的结构体指针

成功返回true,失败请使�?..lasterr()获取错误信息

### crypyAesObject.setKeyParamMode(\_CRYPT\_MODE)

设置加密模式

成功返回true,失败请使�?..lasterr()获取错误信息

### crypyAesObject.setKeyParamPadding(\_PKCS5\_PADDIN)

设置加密填充方式,

PKCS7填充模式请指�?\_PKCS5\_PADDIN,

成功返回true,失败请使�?..lasterr()获取错误信息

### crypyAesObject.setPassword("密钥",选项)

支持128�?16字节)�?92�?24字节) �?256�?32字节)密钥

如果密钥长度不足指定位数自动填充 `'\0'` 到最适合的密钥长�?

超过24字节使用使用MD5算法创建转换�?4位密�?

参数@2不需要指�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/crypt/aes.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/crypt/aes.md')

