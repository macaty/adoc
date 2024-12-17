[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: sqlServer 搴?- MSSQL 瀛樺偍杩囩▼

```aardio aardio
//sqlServer 搴?-  MSSQL 瀛樺偍杩囩▼

import console;
import sqlServer;

//鎵撳紑鏁版嵁搴?var db = sqlServer(
    ["Data Source"]= "IP鍦板潃,鏈嶅姟绔彛";
    ["Database"]= "鏁版嵁搴撳悕";
    ["User ID"]  = "鐢ㄦ埛鍚?;
    ["Password"]= "鐢ㄦ埛瀵嗙爜";
)

//鍒涘缓瀛樺偍杩囩▼
if( ! db.existsProcedure("proc_aardio_test2") ){
    db.exec("
    CREATE PROC proc_aardio_test( @a INT OUTPUT,@b INT )
    AS
    begin
        SET @a=123
        SELECT @a
        SELECT @a + @b
    end
    ");
}

//鍒涘缓鍛戒护鍙傛暟瀵硅薄,鐢ㄤ簬鎵ц瀛樺偍杩囩▼
var cmd = db.createCommand( "proc_aardio_test2" );

//缁戝畾瀛樺偍杩囩▼鍙傛暟
cmd.bind(
    a = 2;
    b = 3;
)

//鎵ц骞舵樉绀虹粨鏋?console.dump(cmd.stepQuery() )

console.dump("杈撳嚭鍙傛暟a鐨勫�?,cmd.parameters("@a").value)

/*
//澶氱粨鏋滈泦鏌ヨ绀轰緥
var rs = cmd.executeRecords();
var data = rs.stepQuery()

//涓嬩竴涓粨鏋滈泦
rs = rs.nextRecordset();
var data = rs.stepQuery()
*/

//鍏抽棴鏁版嵁搴撹繛鎺?db.close();

console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Database/mssql/procedure.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Database/mssql/procedure.md')

