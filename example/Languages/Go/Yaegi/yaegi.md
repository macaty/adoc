[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 Go 语言 yaegi 脚本

```aardio aardio
//aardio 调用 Go 语言 yaegi 脚本

//创建 Yaegi 解释器（同一线程底层只会创建一个解释器环境�?import golang.yaegi;
var go = golang.yaegi();

//直接�?Go 语法写脚本�?//教程: https://mp.weixin.qq.com/s/_YBW0kN2uJ_pBekNF_b0WQ
go.eval(`
package main

//导入模块
import (
    "fmt"
    "os"
)

//编写函数
func SetArgs(args ...string) {
    os.Args = args
}

//编写函数
func SetEnv(key, value string) error {
    return os.Setenv(key, value)
}

//全局变量
var GlobaVal = "这是全局变量";
`)

//�?aardio 中调�?Go 函数
go.SetArgs( "arg1","arg2" )

//�?aardio 中调�?Go 函数
go.SetEnv( "TestKey2","TestValue2" );

//�?aardio 中修�?Go 全局常量的�?go.GlobaVal = "新的 Go 全局常量�?;

import console.int;

//获取 Go 全局常量的�?console.log( go.GlobaVal );

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Go/Yaegi/yaegi.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Go/Yaegi/yaegi.md')

