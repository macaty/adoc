[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 网卡 DNS 修改工具（双�?DNS 修改�?
```aardio aardio
//RUNAS//设置网络连接
import win.ui;
/*DSG{{*/
var winform = win.form(text="网卡 DNS 修改工具（双�?DNS 修改�?;right=1031;bottom=712)
winform.add(
edit={cls="edit";left=25;top=584;right=997;bottom=693;edge=1;multiline=1;z=2};
listview={cls="listview";left=24;top=27;right=996;bottom=555;edge=1;z=1}
)
/*}}*/

import win.ui.grid;
var grid = win.ui.grid(winform.listview);
grid.readonlyColums = { [1] = true ,[4] = true, [5] = true};//设置禁止编辑的列

winform.listview.insertColumn("IP",100)
winform.listview.insertColumn("主DNS",100)
winform.listview.insertColumn("辅DNS",100)
winform.listview.insertColumn("MAC",110)
winform.listview.insertColumn("网卡",-1)

import com.wmi;
var loadNetworks = function(){

    var dataTable = {}
    dataTable.fields = {"ip";"dns1","dns2","mac","description"}

    //com.wmi.eachProperties 返回的是普通表而非 COM 对象
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

//编辑变更值会触发下面的事�?grid.onEditChanged = function(text,iItem,iSubItem){
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
        winform.edit.print("修改成功",itemData[fieldName],"-->",text);
    }
    else {
        winform.edit.print("修改失败，错误代码："+err,itemData[fieldName],"-->",text);
    }

}

/*
用户点击列头排序时会触发下面的事件，
cloumn为例号，desc参数指定是否倒序，返回true允许当前列排�?*/
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

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Network/Manage/wmi.adapter.md)

