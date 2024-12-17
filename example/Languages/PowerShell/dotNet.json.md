[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 PowerShell �?JSON 操作

```aardio aardio
//aardio 调用 PowerShell �?JSON 操作
import console;
import dotNet.ps;
/*
aardio 调用 PowerShell 教程: https://mp.weixin.qq.com/s/Sr4HNkOJ1mmAj_V52v69IA
PowerShell 快速入�?https://learnxinyminutes.com/docs/zh-cn/powershell-cn/
*/

// ConvertTo-Json 自动兼容�?PowerShell 2.0 （Win7 自带�?var psVersion = dotNet.ps.json(`ConvertTo-Json $PSVersionTable.PSVersion`)
console.dumpJson(psVersion);
console.log(err);

//也可以用下面的方�?/*
dotNet.ps 在当前进程运�?PowerShell�?PowerShell 共享 aardio 创建�?.Net 应用程序域�?所�?aardio 加载的内存程序集 Newtonsoft.Json �?PowerShell 里也可以使用�?*/
import dotNet.json;
var json = dotNet.ps( `
    $tab = @{ Name = "张三"; Age = "20"; Array = 1,2,3 } # 哈希�?数组元素要用逗号分开)
    [Newtonsoft.Json.JsonConvert]::SerializeObject(  $tab  )` // PowerShell 类型放在 [] 里面，并�?:: 访问类的静态成�?    );
var psVersion = web.json.parse(json);//解析 JSON
console.dumpJson(psVersion);

//获取 PowerShell 版本也可以这样写
import win.reg;
var psVersion = win.reg.query("HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\PowerShell\3\PowerShellEngine","PowerShellVersion")
    || win.reg.query("HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\PowerShell\1\PowerShellEngine","PowerShellVersion");

console.log("PowerShell 版本:",psVersion);
console.pause(true);

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/PowerShell/dotNet.json.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/PowerShell/dotNet.json.md')

