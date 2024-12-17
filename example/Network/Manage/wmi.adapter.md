[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 缃戝崱 DNS 淇敼宸ュ叿锛堝弻鍑?DNS 淇敼锛?
```aardio aardio
//RUNAS//璁剧疆缃戠粶杩炴帴
import win.ui;
/*DSG{{*/
var winform = win.form(text="缃戝崱 DNS 淇敼宸ュ叿锛堝弻鍑?DNS 淇敼锛?;right=1031;bottom=712)
winform.add(
edit={cls="edit";left=25;top=584;right=997;bottom=693;edge=1;multiline=1;z=2};
listview={cls="listview";left=24;top=27;right=996;bottom=555;edge=1;z=1}
)
/*}}*/

import win.ui.grid;
var grid = win.ui.grid(winform.listview);
grid.readonlyColums = { [1] = true ,[4] = true, [5] = true};//璁剧疆绂佹缂栬緫鐨勫垪

winform.listview.insertColumn("IP",100)
winform.listview.insertColumn("涓籇NS",100)
winform.listview.insertColumn("杈匘NS",100)
winform.listview.insertColumn("MAC",110)
winform.listview.insertColumn("缃戝崱",-1)

import com.wmi;
var loadNetworks = function(){

    var dataTable = {}
    dataTable.fields = {"ip";"dns1","dns2","mac","description"}

    //com.wmi.eachProperties 杩斿洖鐨勬槸鏅�氳〃鑰岄潪 COM 瀵硅薄
    for item in com.wmi.eachProperties("SELECT * FROM Win32_NetworkAdapterConfiguration WHERE IPEnabled=true") {
        if(!item.DNSServerSearchOrder){
            continue;
        }

        //https://docs.microsoft.com/en-us/windows/win32/cimwin32prov/win32-networkadapterconfiguration
        table.push(dataTable,{
            description = item.Description;
            ip = item.IPAddress[1];
            dns1 = item.DNSServerSearchOrder[1];
            dns2 = item.DNSServerSearchOrder[2];
            mac = item.MACAddress;
            settingId = item.SettingID;
        } )
    }

    grid.setTable( dataTable );
    winform.listview.dataTable = dataTable;
}

loadNetworks();

//缂栬緫鍙樻洿鍊间細瑙﹀彂涓嬮潰鐨勪簨浠?grid.onEditChanged = function(text,iItem,iSubItem){
    var dataTable = winform.listview.dataTable;
    var fieldName = dataTable.fields[iSubItem]
    var itemData = dataTable[iItem];

    var adapter = com.wmi.get("SELECT * FROM Win32_NetworkAdapterConfiguration WHERE SettingID=@settingId",itemData);

    var err;
    if(fieldName === "dns1"){
        itemData.dns1 = text;
        err = adapter.SetDNSServerSearchOrder({itemData.dns1,itemData.dns2});

    }
    else if(fieldName === "dns2"){
        itemData.dns2 = text;
        err = adapter.SetDNSServerSearchOrder({itemData.dns1,itemData.dns2});
    }

    //https://docs.microsoft.com/en-us/windows/win32/cimwin32prov/setdnsserversearchorder-method-in-class-win32-networkadapterconfiguration
    if(err==0){
        winform.edit.print("淇敼鎴愬姛",itemData[fieldName],"-->",text);
    }
    else {
        winform.edit.print("淇敼澶辫触锛岄敊璇唬鐮侊細"+err,itemData[fieldName],"-->",text);
    }

}

/*
鐢ㄦ埛鐐瑰嚮鍒楀ご鎺掑簭鏃朵細瑙﹀彂涓嬮潰鐨勪簨浠讹紝
cloumn涓轰緥鍙凤紝desc鍙傛暟鎸囧畾鏄惁鍊掑簭锛岃繑鍥瀟rue鍏佽褰撳墠鍒楁帓搴?*/
grid.onSortColumn = function(cloumn,desc){
    var dataTable = winform.listview.dataTable;
    var name = dataTable.fields[cloumn]

    if(desc){
        table.sort(dataTable,function(b){
            return time(owner[name]) < time(b[name])
        })
    }
    else {
        table.sort(dataTable,function(b){
            return time(owner[name]) > time(b[name])
        })
    }

    grid.setTable( dataTable )
    return true;

}

winform.show();
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Network/Manage/wmi.adapter.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Network/Manage/wmi.adapter.md')

