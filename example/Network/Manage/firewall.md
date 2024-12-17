[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: RUNAS//闃茬伀澧?
```aardio aardio
//RUNAS//闃茬伀澧?import console;
import dotNet.ps;

console.showLoading(" 姝ｅ湪鎵ц娣诲姞闃茬伀澧欒鍒?);

console.log(dotNet.ps.command("New-NetFirewallRule",{
    Name = "FirewallRuleProgram123";
    DisplayName = "闃茬伀澧欐祴璇曠▼搴?23";
    Program = io._exepath;
    Direction = "Inbound";
    Actio n= "Allow";
}));

console.log(dotNet.ps.command("New-NetFirewallRule",{
    Name = "FirewallRulePort123";
    DisplayName = "闃茬伀澧欐祴璇曠鍙?23";
    Direction = "Inbound";
    LocalPort = 8806;
    Protocol = "TCP";
    Action = "Allow";
}));

/*
import process.control;
process.control("firewall.cpl")
*/

console.showLoading(" 姝ｅ湪鎵ц绉婚櫎闃茬伀澧欒鍒?);
console.log(dotNet.ps.command("Remove-NetFirewallRule",{
    Name  = "FirewallRuleProgram123";
}));

console.log(dotNet.ps.command("Remove-NetFirewallRule",{
    Name  = "FirewallRulePort123";
}));

console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Network/Manage/firewall.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Network/Manage/firewall.md')

