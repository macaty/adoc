[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 批处理与环境变量

```aardio aardio
//批处理与环境变量
//相关范例：进�?> 管道
import win;
import process.popen

//在父进程中指定环境变�?string.setenv("TESTENV","测试变量�?);

//也可以用下面的方�?//import environment
//environment.user().set("TESTENV","测试变量�?)

//打开命令�?隐藏命令行窗�?var prcs = process.popen.cmd(`echo %TESTENV%`)

//也可以在 process �?process.popen 参数@3中通过 environment为目标进程指定环境变�?var prcs = process.popen("cmd.exe","/c echo %TESTENV2%",{
    environment = {
        TESTENV2 = "测试变量�?"
    }
})

import fsys.environment;
import process.batch;
var prcs = process.batch( `
@echo off
set TESTENV3=测试变量�?<?
    print( fsys.environment.expand("%appdata%") )

?>&
echo %TESTENV3%
`)

//显示结果
import win;
win.msgbox(prcs.read(-1))

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Bat/env.md)

