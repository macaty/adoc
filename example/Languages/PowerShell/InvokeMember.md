[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: PowerShell 使用 InvokeMember 回调 aardio

```aardio aardio
//PowerShell 使用 InvokeMember 回调 aardio
import win;
import console;
console.showLoading(" 正在执行 PowerShell 命令");

/*
aardio 调用 PowerShell 教程: https://mp.weixin.qq.com/s/Sr4HNkOJ1mmAj_V52v69IA
PowerShell 快速入�?https://learnxinyminutes.com/docs/zh-cn/powershell-cn/

Win10/Win11 自带�?PowerShell 5.1 已经可以直接回调参数中的 aardio 对象�?如果希望兼容�?Win7 自带�?PowerShell 2.0，则可用 dotNet.ps.export() 导出 aardio 对象�?PowerShell �?
只要简洁，不求完美�?Win7 在市场上已经接近消失，现在开发软件再处处考虑 Win7 兼容是不必要的�?*/
import dotNet.ps;

//PowerShell 脚本代码
var pScript = /*
    # 定义命名参数，参数前�?号，aardio 参数表里去掉$�?    param($win,$external,$username)

    # 使用 InvokeMember 调用参数传进来的 aardio 对象，参�?@1 指定成员函数�?    $win.InvokeMember("msgboxTest","这是 PowerShell 调用 aardio 打开的对话框�?) #返回值会自动输出一�?
    # 可以直接读写属性，这里用下标也可以
    $external.abc = 123

    # 自由调用 aardio 函数
    $external.InvokeMember("func","参数1","参数2")

    # 遍历所有匿名参数，有名字的参数这里不输�?    for ( $i=0; $i -lt $args.count; $i++){
        #write-host $args[$i]
    }

    Write-Host ("username: " + $username[0])
    Write-Output "测试输出"

    $PSVersionTable.PSVersion
*/

var output,err = dotNet.ps(pScript,{
    //等号前面是参数名（必须是字符串），等号后面是参数值（可传�?.Net 对象、COM 对象、aardio 对象�?    win = dotNet.ps.export(win); //参数名前不要�?�?
    external = dotNet.ps.export({
        func = function(...){
            console.log("PowerShell 调用 aardio，参数：",...)
            console.dump(owner)
        }
    });
    username = {"测试名字"};//不需要回调成员函数的普通数组，不需要用 dotNet.ps.export 转换�?    "匿名参数1","匿名参数2","匿名参数3","匿名参数4"
});

console.log(output,err);
console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/PowerShell/InvokeMember.md)

