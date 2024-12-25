[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 Go 语言 yaegi 脚本 - 提取符号�?
```aardio aardio
//aardio 调用 Go 语言 yaegi 脚本 - 提取符号�?//教程: https://mp.weixin.qq.com/s/_YBW0kN2uJ_pBekNF_b0WQ
import console.int;
import golang;

var go = golang("/","1.22.3")

//创建项目
go.mod("init excelize")

//先要安装模块
go.get("github.com/xuri/excelize/v2")

//再生成符号表
go.yaegiExtract("github.com/xuri/excelize/v2")

/*
运行完成会生�?github_com-xuri-excelize-v2.go

先定义一个全局变量
var Symbols = map[string]map[string]reflect.Value{}

然后加上 github_com-xuri-excelize-v2.go 生成�?Symbols["github.com/xuri/excelize/v2/excelize"] = map[string]reflect.Value{
    //注意上面的键名是包路�?"github.com/xuri/excelize/v2/" 尾部要再加上符号�?"excelize"
    //这里一大堆自动生成的人码�?}

然后创建 Yaegi 解释器的时候注册符号表

yaegiInterpreter = interp.New(interp.Options{})
yaegiInterpreter.Use(stdlib.Symbols)
yaegiInterpreter.Use(Symbols);

然后就可以用了�?
�?Yaegi 脚本里仍然要引入模块�?
import (
    "github.com/xuri/excelize/v2"
)

其实这个模块已经�?Yaegi 里了，不用再下载安装�?*/

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Go/Yaegi/yaegi.Symbols.md)

