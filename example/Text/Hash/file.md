[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 加解密文�?
```aardio aardio
//加解密文�?import console;
import console.progress;
var bar = console.progress();

//创建 AES 加密算法容器
import crypt.aes;
var aes = crypt.aes();// crypt.aes,crypt.rc4 用法相同

//设置密码
aes.setPassword("1234567812345678");

//加密文件，可选用参数 @3 指定分块大小（字节单位），默认为 1MB�?aes.encryptFile(
    "/待加密文�?txt",//参数可传入文件路径或已打开的文件对象�?    "/加密文件.bin",//参数可传入文件路径或已打开的文件对象�?    0x100000,//分块大小，省略则默认�?1MB
    function(totalSize,readSize){//可选指定进度回调参�?        bar.setProgress(readSize/totalSize *100," 正在加密");
    }
)

bar.reset();

//解密文件，可选用参数 @3 指定分块大小（字节单位），默认为 1MB�?aes.decryptFile(
    "/加密文件.bin",//参数可传入文件路径或已打开的文件对象�?    "/解密文件.txt",//参数可传入文件路径或已打开的文件对象�?    0x100000,//分块大小，省略则默认�?1MB
    function(totalSize,readSize){//可选指定进度回调参�?        bar.setProgress(readSize/totalSize*100," 正在解密");
    }
)

//如果希望速度更快，可以不指定进度回调函数，或者加大分块大�?
```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Text/Hash/file.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Text/Hash/file.md')

