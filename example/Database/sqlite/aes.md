[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: sqlite �?- 加密算法

```aardio aardio
//sqlite �?- 加密算法
import console;
import sqlite.ciphers;

//打开加密数据库（只有输入正确密钥才能读写数据库）
var db = sqlite.ciphers("file:/sqlCiphers.DB",{
    //参数 @1 如果�?file: 开头的 URI ，下面就可以指定 URI 参数�?    cipher="sqlcipher";//加密算法
    legacy=3;//SqlCiphers 兼容版本
    kdf_iter=4000;
    legacy_page_size=1024;
    hmac_use=0;
}  )

/*
//如果上面不指定加密配置，可以调用下面的函数：
//加密配置: https://utelle.github.io/SQLite3MultipleCiphers/docs/ciphers/cipher_sqlcipher/
db.config("cipher","sqlcipher"); //加密算法
db.configCipher("sqlcipher","legacy",3);//加密参数
*/

//单独设置密码(URI 参数一般不用于指定密码)
db.key("密码");

//创建�?if( not db.existsTable("film") ){
    db.exec( "CREATE TABLE film(title, length, year, starring);")
}

//创建预处理命�?var cmd = db.prepare("INSERT INTO film values (@title,@length,@year, 'Jodie Foster');" )

//提交更改
cmd.step( {
    "title":"标题";
    "length":4;
    "year":time.now();
} );

cmd.finalize(); //释放对象

//迭代方式查询数据
for title, length, year, starring in db.each("SELECT * FROM film") {
    console.log( title, length, year, starring  )
}

console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Database/sqlite/aes.md)

