[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: RUNAS// 修复更新

```aardio aardio
//RUNAS// 修复更新
import fsys;
import service;
import console;

console.log("Windows 10 如果反复更新失败，或更新后导致系统无法启动，
即使下载新版操作系统安装程序也提�? '无法确定你的电脑能否安装 Win10',
这很可能是因为引导分区导致的问题，解决这个问题的方法�?
    1.使用 U盘启�?Win10 PE 系统
    2.运行 DiskGenius 删除系统硬盘�?ESP、MSR、Recovery 分区，这些分区都很小，小心不要删错了�?    3.DiskGenius 里在操作系统硬盘重新创建 ESP 分区
    4.打开 DISM++ 修复引导（选中原来的操作系统硬盘，不是PE分区�?    5.这里 https://go.microsoft.com/fwlink/?LinkId=691209 下载 MediaCreationTool 安装最新系�?
上面的方法仅供参考，使用上面的方案一切风险自负�?)

console.more(1,true)

if(!console.askYesNo("如果你暂时不想尝试重建引导分区的方法�?你可以继续运行本工具尝试重置和修复系统自动更新工具，本工具不作任何保证，
使用本工具一切后果自负，�?Y 键继续操�?�?N 键取�?)) return;
console.pause(true);

var stopService = function(serviceName){
    console.showLoading(" 正在停止 " + serviceName + " 服务");
    sleep(1000);

    var ret = service.stop(serviceName);
    console.log(ret?"成功":"失败");
    sleep(3000);
}

stopService("wuauserv");
stopService("cryptSvc");
stopService("bits");
stopService("msiserver");

import fsys;
fsys.enum( io.getSpecial(0x23/*_CSIDL_COMMON_APPDATA*/,"\Application Data\Microsoft\Network\Downloader\"),
    {"qmgr*.dat","qmgr.db","qmgr.jfm"},
    function(dir,filename,fullpath,findData){
        if(filename){
            console.log("正在删除�?+filename)
            fsys.delete(fullpath);
        }
    }
);

var path = io.getSpecial(0x24 /*_CSIDL_WINDOWS*/,"SoftwareDistribution/Download");
fsys.enum( path, "*.*",
    function(dir,filename,fullpath,findData){
        fsys.delete(fullpath)
        console.log("正在删除",filename:dir)
    },false
);

var path = io.getSpecial(0x24 /*_CSIDL_WINDOWS*/,"SoftwareDistribution/DataStore");
fsys.enum( path, "*.*",
    function(dir,filename,fullpath,findData){
        fsys.delete(fullpath)
        console.log("正在删除",filename:dir)
    },false
);

console.showLoading("正在重置安全编录数据库文�?");

import fsys.acl;
fsys.acl.takeOwn("C:\Windows\system32\catroot2");
var ret = fsys.rename("C:\Windows\system32\catroot2","C:\Windows\system32\catroot2.old");
console.log(ret?"成功":"失败");

console.showLoading("正在重置安全编录数据库文�?");
var ret = fsys.delete("C:\Windows\system32\catroot2.old");
console.log(ret?"成功":"失败");

console.showLoading("正在重置自动更新目录");
import fsys.acl;
fsys.acl.takeOwn("C:\Windows\SoftwareDistribution");
var ret = fsys.delete("C:\Windows\SoftwareDistribution");
console.log(ret?"成功":"失败");

import process.batch;
var prcs = process.batch.wow64(`
sc.exe sdset bits D:(A;;CCLCSWRPWPDTLOCRRC;;;SY)(A;;CCDCLCSWRPWPDTLOCRSDRCWDWO;;;BA)(A;;CCLCSWLOCRRC;;;AU)(A;;CCLCSWRPWPDTLOCRRC;;;PU)
sc.exe sdset wuauserv D:(A;;CCLCSWRPWPDTLOCRRC;;;SY)(A;;CCDCLCSWRPWPDTLOCRSDRCWDWO;;;BA)(A;;CCLCSWLOCRRC;;;AU)(A;;CCLCSWRPWPDTLOCRRC;;;PU)

for %%1 in (%windir%\system32\*.dll) do regsvr32.exe /s %%1

netsh winsock reset

bitsadmin.exe /reset /allusers
`)

for( all,out,err in prcs.each() ){
    io.stdout.write( out,err );
}

var startService = function(serviceName){
    console.showLoading(" 正在启动 " + serviceName + " 服务");
    sleep(1000);

    var srvMgr = service.manager();

    srvMgr.startAutomatic(serviceName);
    var ret = srvMgr.isRunning(serviceName)  || srvMgr.start(serviceName);
    console.log(ret?"成功":"失败");
    sleep(3000);
}

startService("wuauserv");
startService("cryptSvc");
startService("bits");
startService("msiserver");

var prcs = process.batch.wow64(`
wuauclt /resetauthorization
wuauclt /detectnow
usoclient startscan
`)
for( all,out,err in prcs.each() ){
    io.stdout.write( out,err );
}

if( console.askYesNo("是否调用 DISM 修复系统文件") ) {

    /*
    /Online 选项指的是修复当前正在运行的 Windows 系统�?    也可以修复其他分区未加载�?Windows ，例如加上用C:\Windows去修�?D:\ 盘的 Windows
    process("DISM.exe /Image:D:\ /Cleanup-image /Restorehealth /Source:C:\Windows")
    */
    import process;
    process("DISM.exe /Online /Cleanup-image /Restorehealth").wait()

    //sfc /scannow 命令将扫描所有受保护的系统文件，并用位于 %WinDir%\System32\dllcache 的压缩文件夹中的缓存副本替换损坏的文件�?    //process("sfc /scannow").wait();
}

if( console.askYesNo("是否下载并运行微软升级系统工�?MediaCreationTool") ) {
    import fsys.wow64;
    fsys.wow64.disableRedirection(
        function(){
            import inet.installer
            inet.installer("MediaCreationTool","https://go.microsoft.com/fwlink/?LinkId=691209")
        }
    )
}

console.log("全部操作已完成�?);
console.pause(true);

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/System/Settings/fixUpdate.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/System/Settings/fixUpdate.md')

