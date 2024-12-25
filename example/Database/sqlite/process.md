[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: sqlite �?- 加密算法（命令行�?
```aardio aardio
//sqlite �?- 加密算法（命令行�?import console.int;
import process.sqlCipher;

//数据库文件可指定中文路径、相对路径、URI 路径。指�?"--help" 参数列出所有可用参�?var db = process.sqlCipher("sqlCiphers.DB",{csv=true});

//写入 SQL 指令并关闭输�?db.writeClose(`
PRAGMA cipher_compatibility = 3;
PRAGMA key = '密码';
PRAGMA cipher_use_hmac = OFF;
PRAGMA cipher_page_size = 1024;
PRAGMA kdf_iter = 4000;
SELECT * FROM film;
`)

//回显输出
db.logResponse();

/*

//读取所有输出，要去掉前面的 db.logResponse();
var csv = db.readAll();

//解析 CSV
import string.database;
var tab = string.database(",").parse( csv );
console.dumpJson(tab);

*/

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Database/sqlite/process.md)

