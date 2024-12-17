[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: sqlite 搴?- 鍔犲瘑绠楁硶

```aardio aardio
//sqlite 搴?- 鍔犲瘑绠楁硶
import console;
import sqlite.ciphers;

//鎵撳紑鍔犲瘑鏁版嵁搴擄紙鍙湁杈撳叆姝ｇ‘瀵嗛挜鎵嶈兘璇诲啓鏁版嵁搴擄級
var db = sqlite.ciphers("file:/sqlCiphers.DB",{
    //鍙傛暟 @1 濡傛灉鏄?file: 寮�澶寸殑 URI 锛屼笅闈㈠氨鍙互鎸囧畾 URI 鍙傛暟琛?    cipher="sqlcipher";//鍔犲瘑绠楁硶
    legacy=3;//SqlCiphers 鍏煎鐗堟湰
    kdf_iter=4000;
    legacy_page_size=1024;
    hmac_use=0;
}  )

/*
//濡傛灉涓婇潰涓嶆寚瀹氬姞瀵嗛厤缃紝鍙互璋冪敤涓嬮潰鐨勫嚱鏁帮細
//鍔犲瘑閰嶇疆: https://utelle.github.io/SQLite3MultipleCiphers/docs/ciphers/cipher_sqlcipher/
db.config("cipher","sqlcipher"); //鍔犲瘑绠楁硶
db.configCipher("sqlcipher","legacy",3);//鍔犲瘑鍙傛暟
*/

//鍗曠嫭璁剧疆瀵嗙爜(URI 鍙傛暟涓�鑸笉鐢ㄤ簬鎸囧畾瀵嗙爜)
db.key("瀵嗙爜");

//鍒涘缓琛?if( not db.existsTable("film") ){
    db.exec( "CREATE TABLE film(title, length, year, starring);")
}

//鍒涘缓棰勫鐞嗗懡浠?var cmd = db.prepare("INSERT INTO film values (@title,@length,@year, 'Jodie Foster');" )

//鎻愪氦鏇存敼
cmd.step( {
    "title":"鏍囬";
    "length":4;
    "year":time.now();
} );

cmd.finalize(); //閲婃斁瀵硅薄

//杩唬鏂瑰紡鏌ヨ鏁版嵁
for title, length, year, starring in db.each("SELECT * FROM film") {
    console.log( title, length, year, starring  )
}

console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Database/sqlite/aes.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Database/sqlite/aes.md')

