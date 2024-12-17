[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: PowerShell 回调 aardio

```aardio aardio
//PowerShell 回调 aardio
import win;
import console.int;
import dotNet.ps;
/*
aardio 调用 PowerShell 教程: https://mp.weixin.qq.com/s/Sr4HNkOJ1mmAj_V52v69IA
PowerShell 快速入�?https://learnxinyminutes.com/docs/zh-cn/powershell-cn/
*/

// PowerShell 脚本代码
var pScript = /*
    # 定义命名参数，参数前�?号，aardio 参数表里去掉$�?    param($win,$external,$username) # 类似�?aardio 中展开不定参数 $win,$external,$username = ...

    # 自由调用参数传进来的 aardio 对象
    $win.msgboxTest("这是 PowerShell 调用 aardio 打开的对话框�?) #返回值会自动输出一�?
    # 自由调用 aardio 函数
    $external.func("参数1","参数2")

    # 遍历所有匿名参数，有名字的参数这里不输�?    for ( $i=0; $i -lt $args.count; $i++){
        # Write-Host $args[$i]
    }

    Write-Host ("username: " + $username)
    Write-Output "测试输出"
*/

var output,err = dotNet.ps(pScript,{
    //等号前面是参数名（必须是字符串），等号后面是参数值（可传�?.Net 对象、COM 对象、aardio 对象�?    win = win; //参数名前不要�?�?
    external = {
        func = function(...){
            console.log("PowerShell 调用 aardio，参数：",...)
        }
    };
    username = "测试名字";
    "匿名参数1","匿名参数2","匿名参数3","匿名参数4"
});

console.log(output);
if(err) console.log("
Win10/Win11 自带�?PowerShell 5.1 已经可以直接回调参数中的 aardio 对象�?如果希望兼容�?Win7 自带�?PowerShell 2.0，则可用 dotNet.ps.export() 导出 aardio 对象�?PowerShell �?
只要简洁，不求完美�?Win7 在市场上已经接近消失，现在开发软件再处处考虑 Win7 兼容是不必要的�?");

/*
dotNet.ps 在当前进程创建新的线程运�?PowerShell�?PowerShell 运行�?aardio �?dotNet.appDomain() 创建的默认应用程序域内�?process.popen.ps 则是创建新的子进程运�?PowerShell，并通过管道获取进程输出�?*/
console.log(dotNet.ps(`[System.AppDomain]::CurrentDomain`))

//上面是执�?PowerShell 脚本，下面是执行 PowerShell 命令，参数用法基本一�?console.showLoading(" 正在执行 PowerShell 命令");
var output = dotNet.ps.command("Get-Command",{Name="*Process"});

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/PowerShell/dotNet.ps.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/PowerShell/dotNet.ps.md')

