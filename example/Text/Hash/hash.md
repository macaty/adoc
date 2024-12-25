[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: MD5,SHA-1

```aardio aardio
//MD5,SHA-1
import crypt;
import console;

//等待md5加密的字�?var str1 = "12345678901234567890123456789012345678901234567890123456789012345678901234567890";

console.log(  '\r\n使用标准库crypt.md5()函数计算的md5�?32�?16�?�? , '\r\n'
    , crypt.md5(str1),crypt.md5(str1,,true)  )

console.log( '\r\n使用标准库crypt.sha1()函数计算的sha1值：','\r\n'
    ,crypt.sha1(str1)  )

console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Text/Hash/hash.md)

