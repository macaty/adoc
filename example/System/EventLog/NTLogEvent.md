[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鏌ヨ绯荤粺鏃ュ織

```aardio aardio
//鏌ヨ绯荤粺鏃ュ織
import console.int;
import com.wmi;
import sys.acl;

for event in com.wmi.eachProperties(`SELECT * FROM Win32_NTLogEvent WHERE
     Logfile = "System" AND ( EventCode=7001 OR EventCode=7002 OR EventCode=6005 OR EventCode=6006 )` ) {
/*
    console.log( "Category: ", event.Category);
    console.log( "Computer Name: ", event.ComputerName);
    console.log( "Event Code: ", event.EventCode);
    console.log( "Message: ", event.Message);
    console.log( "Record Number: ", event.RecordNumber);
    console.log( "Source Name: ", event.SourceName);
    console.log( "Event Type: ", event.Type);
    console.log( "User: ", event.User);
    console.dumpTable(event)
*/

    var tm = time.utc( event.TimeWritten ).local();

    if(event.EventCode==7001 && event.SourceName=="Microsoft-Windows-Winlogon"){
        var idx,sid = table.find(event.InsertionStrings,lambda(v) string.startWith(v,"S-"));
        var userName = sys.acl.sidStringToUserName(sid);

        console.log(tm,userName + " 鐧诲綍鎴愬姛")
    }
    if(event.EventCode==7002 && event.SourceName=="Microsoft-Windows-Winlogon"){
        var idx,sid = table.find(event.InsertionStrings,lambda(v) string.startWith(v,"S-"));
        var userName = sys.acl.sidStringToUserName(sid);

        console.log(tm,userName, " 宸叉敞閿�" )
    }
    elseif(event.SourceName=="EventLog") {
        console.log(tm,event.Message,event.SourceName,event.EventCode)
        if(event.EventCode == 6005) console.more(1)
    }
}

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/System/EventLog/NTLogEvent.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/System/EventLog/NTLogEvent.md')

