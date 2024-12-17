[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 通过进程管道调用 PowerShell

```aardio aardio
//aardio 通过进程管道调用 PowerShell
import console.int;
import process.popen;

/*
调用 PowerShell.exe 执行 PowerShell 命令�?参数说明请参�?https://learn.microsoft.com/powershell/module/microsoft.powershell.core/about/about_powershell_exe
*/
var ps = process.popen.ps("-Command","Write-Output $PSVersionTable.PSVersion");

//这样写为之个参数也可�?var ps = process.popen.ps("-Command","Write-Output","$PSVersionTable.PSVersion");

/*
传多个命令行参数时，
单个参数如果首尾没有双引号，且包含空白字符、双引号等需要转义的字符�?aardio 会自动在首尾添加双引号并进行尾要的转义�?
�?PowerShell 命令首尾�?{ } 包起来，表示这是一�?PowerShell 语句�?最前面再加�?& 表示执行 PowerShell 语句�?
这时候因为在 { } 内部的双引号并没有出现在参数首尾�?aardio 就会自动处理命令行参数转义并再次在参数首尾添加双引号�?PowerShell 就可以得到正确参数�?*/
var ps = process.popen.ps(`-Command`,`&{Get-FileHash "` + io._exepath + `"}`);

/*
返回�?ps �?process.popen 对象，提供大量读写与操作进程管道的函数�?例如直接读取 PowerShell 进程全部输出�?*/
//var str = ps.readAll();

//自动输出到控制台
ps.logResponse(); //也可以输出到文本�?ps.logResponse(winform.edit)

//�?PowerShell 输出转换�?JSON
var ps  = process.popen.ps(`-Command`,`&{
    # PowerShell 会将仅用大括号包含的 PowerShell 作为字符串输出​，
    # 在前面加上一�?& 字符才会执行该语句块�?
    # PowerShell 2.0 不支�?ConvertTo-Json，这里先打个补丁
    # Win10/Win11 已经自带 PowerShell 5.x，如果不想支持古老的 Win7，这段兼容代码可以不加�?    if ($PSVersionTable.PSVersion.Major -lt 3){
        Add-Type -assembly system.web.extensions
        function ConvertTo-Json([object] $item){
            $jss=New-Object system.web.script.serialization.javascriptSerializer
            return $jss.Serialize($item)
        }
    };

    function Get-Version {
        ConvertTo-Json( $PSVersionTable.PSVersion )
    }

    Get-Version

}`);

//读取进程 JSON 输出
var psVersion = ps.jsonAll()

console.dump(psVersion);
console.pause();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/PowerShell/process.popen.ps.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/PowerShell/process.popen.ps.md')

