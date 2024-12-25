[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: RUNAS//防火�?
```aardio aardio
//RUNAS//防火�?import console;
import dotNet.ps;

console.showLoading(" 正在执行添加防火墙规�?);

console.log(dotNet.ps.command("New-NetFirewallRule",{
    Name = "FirewallRuleProgram123";
    DisplayName = "防火墙测试程�?23";
    Program = io._exepath;
    Direction = "Inbound";
    Actio n= "Allow";
}));

console.log(dotNet.ps.command("New-NetFirewallRule",{
    Name = "FirewallRulePort123";
    DisplayName = "防火墙测试端�?23";
    Direction = "Inbound";
    LocalPort = 8806;
    Protocol = "TCP";
    Action = "Allow";
}));

/*
import process.control;
process.control("firewall.cpl")
*/

console.showLoading(" 正在执行移除防火墙规�?);
console.log(dotNet.ps.command("Remove-NetFirewallRule",{
    Name  = "FirewallRuleProgram123";
}));

console.log(dotNet.ps.command("Remove-NetFirewallRule",{
    Name  = "FirewallRulePort123";
}));

console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Network/Manage/firewall.md)

