[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 注册表操�?- WoW64 重定�?
```aardio aardio
//注册表操�?- WoW64 重定�?import win.reg;
/*
64 位操作系�?�?WoW64 模式默认会存在注册表与文件系统自动重定向�?
所以，打开注册看到某个注册表键值，
可能并不一定就是程序中实际读写的键值�?
在某些情况下�?我们可能需要暂时禁�?WoW64 重定向以查询 64 位注册表�?*/

//方法一：禁�?WoW64 重定向，查询 64 位注册表路径
var v = win.reg.queryWow64( "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\SoftwareProtectionPlatform"
        ,"BackupProductKeyDefault" )

//方法二：禁用 WoW64 重定向，打开  64 位注册表
var reg = win.regWow64("HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\SoftwareProtectionPlatform",true)
if(reg){
    var v = reg.queryValue("BackupProductKeyDefault");
}

/*
其他禁用 WoW64 重定向有关的库与函数�?
fsys.wow64;
win.regWow64;
process.wow64;
process.popen.cmd64;
process.popen.bind64;
*/

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/System/Registry/wow64.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/System/Registry/wow64.md')

