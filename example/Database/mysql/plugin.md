[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: mysql.client 搴?- 鐧诲綍鎻掍欢

```aardio aardio
//mysql.client 搴?- 鐧诲綍鎻掍欢
import console;
import mysql.client;
//瀵煎叆 caching_sha2_password 鎻掍欢锛圡ySQL 8.0 榛樿鐧诲綍璁よ瘉鏂瑰紡锛夛紝
import mysql.plugin.cachingSha2Password;

/*
鏈湴鐧诲綍娌″繀瑕佸惎鐢ㄨ繖涓彃浠讹紝鍙敤涓嬮潰鐨?SQL 绂佺敤 caching_sha2_password銆?ALTER USER '鐢ㄦ埛鍚?@'localhost' IDENTIFIED WITH mysql_native_password BY '瀵嗙爜';
*/

console.showLoading(" 姝ｅ湪杩炴帴娴嬭瘯鏁版嵁搴? )
var dbClient,err = mysql.client(
    server = "db4free.net"; //鏁版嵁搴撴湇鍔″櫒,鍙渷鐣ラ粯璁や负localhost
    uid = "aardio_mysql";//鐢ㄦ埛鍚?鍙渷鐣ラ粯璁や负root
    pwd = "aardio.com";
);

if(!dbClient){
    console.log("濡傛灉鏄湁浜烘棤鑱婁慨鏀逛簡瀵嗙爜,璇疯嚜琛屽埌 db4free.net 鐢宠鍏嶈垂鏁版嵁搴?)
    return console.logPause(err);
}

console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Database/mysql/plugin.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Database/mysql/plugin.md')

