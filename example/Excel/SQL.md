[aardio 鏂囨。](../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: SQL 鎿嶄綔

```aardio aardio
//SQL 鎿嶄綔
import access;//浠呬娇鐢ㄧ郴缁熺粍浠?涓嶉渶瑕佸畨瑁?Access / Excel
//import access.oleDb; //瀵煎叆姝ゅ簱鏀寔 *.xlsx 锛屽彲鎸夐渶瀹夎 Microsoft.Ace.OLEDB.16 椹卞姩銆?
//鍙嚜鍔ㄥ垱寤烘枃浠讹紝绯荤粺鑷甫椹卞姩鍙敮鎸?*.xls 鏂囦欢 Excel 8.0( 97-2003 )  鏍煎紡銆?var db,err = access( "/test.xls")

/*
//榛樿鑷姩閰嶇疆杩炴帴鍙傛暟锛屼絾涔熷彲浠ュ涓嬫樉寮忔寚瀹氬弬鏁?var db,err = access( "/test.xlsx",
    {
        ["Provider"] = "Microsoft.Ace.OLEDB.16.0";
        ["Extended Properties"] = "Excel 12.0 Xml;HDR=YES"; //XML 鏍煎紡鐗堟湰鍙湁 12.0锛屼笉瀛樺湪 16.0
    }
)

鍏充簬鍒楁暟鎹被鍨嬩笉缁熶竴鏃跺�间涪澶辨垨瀛楃涓茶鎴柇,鎴栦娇鐢?Excel 婧愮殑鍏朵粬闂,鍙弬鑰冧互涓嬮摼鎺ワ細
https://learn.microsoft.com/zh-cn/sql/integration-services/data-flow/excel-source?view=sql-server-ver16
http://www.connectionstrings.com/excel/
*/

//鍒涘缓琛?if( ! db.existsTable( "sheet1" ) ){
    db.exec("CREATE TABLE sheet1 (username VARCHAR(255),comment MEMO,num double )");
}

//鎻掑叆鏁版嵁,娉ㄦ剰璁块棶excel閲岀殑琛ㄥ悕鍚庨潰鍔?骞剁敤鏀惧埌鏂规嫭鍙烽噷
db.exec( "INSERT INTO [sheet1$](username,comment,num)values('aardio','www.aardio.com',123)");

//鏌ヨ
import console;
for(rs in db.each("SELECT * FROM [sheet1$]") ){
    console.log( rs("username").value );
    console.log( rs("comment").value );
    console.log( rs("num").value )
}

//鍏抽棴鏁版嵁搴?db.close();
console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Excel/SQL.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Excel/SQL.md')

