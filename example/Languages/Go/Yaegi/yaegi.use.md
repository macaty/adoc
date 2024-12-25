[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 Go 语言 yaegi 脚本 - 第三方模�?
```aardio aardio
//aardio 调用 Go 语言 yaegi 脚本 - 第三方模�?import console.int;
assert(_WIN10_LATER,"操作系统版本太低");
import golang.excelize;

//创建 Yaegi（Go 脚本）解释器
//教程: https://mp.weixin.qq.com/s/_YBW0kN2uJ_pBekNF_b0WQ
var go = golang.excelize();

//直接�?Go 语法写脚本�?go.eval(`
package main

import (
    "fmt"
    "github.com/xuri/excelize/v2"
)

func CreateExcel(path string)  string {

   //下面�?Excelize 官网范例
    f := excelize.NewFile();

    defer func() {
        if err := f.Close(); err != nil {
            fmt.Println(err)
        }
    }()

    // 创建新表�?
    index, err := f.NewSheet("Sheet2")
    if err != nil {
        fmt.Println(err)
        return ""
    }

    // 设置单元格的�?
    f.SetCellValue("Sheet2", "A2", "Hello world.")
    f.SetCellValue("Sheet1", "B2", 100)

    // 设置工作簿的当前激活表�?    f.SetActiveSheet(index)

    // 保存表格到指定的路径
    if err := f.SaveAs(path); err != nil {
        fmt.Println(err)
    }

    //读单元格的�?    cell, err := f.GetCellValue("Sheet1", "B2")
    if err != nil {
        fmt.Println(err)
        return ""
    }

    return cell;
}

var GlobaVal = "这是全局变量";
`)

//准备调用参数
var path = io.fullpath("/hha.xlsx");

//�?aardio 中直接调�?Go 函数
var ret = go.CreateExcel( path );

//查看 Go 函数的返回�?console.log( ret );

//�?aardio 中修�?Go 全局常量的�?go.GlobaVal = "新的 Go 全局常量�?;

//获取 Go 全局常量的�?console.log( go.GlobaVal );

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Go/Yaegi/yaegi.use.md)

