[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: sqlite 搴?- replace 璇彞

```aardio aardio
//sqlite 搴?- replace 璇彞
import sqlite;
import console;

//鎵撳紑鍐呭瓨鏁版嵁搴?var db = sqlite(":memory:");
if( not db.existsTable("tableName2") ){

    //鍒涘缓鍗曚富閿〃
    db.exec( "CREATE TABLE tableName(title PRIMARY KEY, length, tm);" )

    //鍒涘缓鍙屼富閿〃
    db.exec( "CREATE TABLE tableName2(title,length,tm,  constraint pk_tableName2 PRIMARY KEY (title,length) );")
}

//replace璇彞鏍规嵁涓婚敭鏌ヨ,涓嶅瓨鍦ㄧ浉鍚屾暟鎹垯鎻掑叆鏂扮殑,鍚﹀垯鏇存柊宸插瓨鍦ㄧ殑鏁版嵁
db.exec( "REPLACE INTO tableName VALUES ('Silence of the Lambs, The', 11.8, datetime('now','localtime')  );")
db.exec( "REPLACE INTO tableName2 VALUES @values;",{
    values  = {
        { 'Contact', 32, time.now() },
        { 'Contact', 16, time.now() }
    }
})

/*
REPLACE INTO 蹇呴』瑕佽缃墍鏈夋棤榛樿鍊煎瓧娈电殑鍊?
濡傛灉瑕佸湪鎻掑叆鍐茬獊鏃朵慨鏀归儴鍒嗗瓧娈?璇风敤涓嬮潰鐨勬柟娉?*/
db.exec("
    INSERT OR IGNORE INTO tableName (title,length,tm) VALUES (@title,@length,@tm);
    UPDATE tableName SET tm=@tm WHERE title=@title",{
        title = 'Silence of the Lambs, The';
        length = 123;
        tm = "456"
    } )

for title,length,tm in db.each("SELECT * FROM tableName") {
    console.log( title,length,tm );
}

for title,length,tm in db.each("SELECT * FROM tableName2") {
    console.log( title,length,tm );
}

db.close();
console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Database/sqlite/replace.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Database/sqlite/replace.md')

