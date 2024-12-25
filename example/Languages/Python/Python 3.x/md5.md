[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 Python 计算 MD5

```aardio aardio
//aardio 调用 Python 计算 MD5
import console;
import py3;

//导入python模块
var hashlib = py3.import("hashlib");

//创建python对象
var md5 = hashlib.md5()

//参数为python中的bytes,在aardio要使用buffer(字节数组)
md5.update( raw.buffer("注意这个函数的参数不是字符串而是字节数组（相当于aardio中的buffer�?) );

console.log( md5.hexdigest() );

import crypt;
console.log( crypt.md5("注意这个函数的参数不是字符串而是字节数组（相当于aardio中的buffer�?) )
console.pause()

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python 3.x/md5.md)

