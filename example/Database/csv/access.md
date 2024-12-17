[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: SQL 璇诲啓 CSV

```aardio aardio
//SQL 璇诲啓 CSV
//涓嬮潰鐨勪唬鐮佷粎浣跨敤绯荤粺缁勪欢,涓嶉渶瑕佸畨瑁?Access 杞欢
import access;
import console;

var txt = /*
Name,Starred,Contact_Id
"瀛熻讲","0",0
"寮犱節榫?,"1",1
*/

//鍒涘缓娴嬭瘯鐨凾XT鏁版嵁搴擄紝access 璇诲啓鐨?CSV 蹇呴』鏄?ANSI 缂栫爜銆?string.save("/Contact.csv",string.fromto(txt) );

//鎸囧畾 CSV 鍒嗛殧绗?涓嶆槸榛樿鐨勯�楀彿灏辫鍦ㄨ繖閲屾敼
import fsys.ini;
var schema = fsys.ini("/schema.ini");
schema.write("Contact.csv","Format","Delimited(,)");

//鍒涘缓 CSV 鏁版嵁搴擄紝鍙傛暟鎸囧畾 CSV 鏂囦欢鎵�鍦ㄧ洰褰曞氨鍙互浜?var csv = access( "/" );

//鏌ヨ骞堕亶鍘嗘暟鎹?for(rs in csv.each("SELECT * FROM [Contact.csv] " ) ){
     console.log( rs("Name").value,rs("Starred").value    );
}

//鍏抽棴 CSV 鏁版嵁搴?csv.close();
console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Database/csv/access.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Database/csv/access.md')

