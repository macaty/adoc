[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 批量执行 CMD 命令

```aardio aardio
//aardio 批量执行 CMD 命令
//相关范例：进�?> 管道

import process.popen

//打开命令�?隐藏命令行窗�?var prcs = process.popen.cmd(`
CD "C:\Program Files"
C:
dir
mkdir test
rmdir test
`)

//显示结果
import win;
win.msgbox(prcs.readAll())

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Bat/cmd.md)

