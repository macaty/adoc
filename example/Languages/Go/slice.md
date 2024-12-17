[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 Go 语言 - 切片

```aardio aardio
//aardio 调用 Go 语言 - 切片
import golang;
var go = golang();
go.main = /**********
package main

import "C"
import "sort"

//export TestSlice
func TestSlice(vals *[]int) {

    //操作 aardio 传过来的切片对象�?golang.slice 对象）�?    sort.Ints(*vals)
}

func main() {}
**********/
go.buildShared("/.go/TestSlice.go");

//------------------下面调用 DLL-----------------------

import console.int;
var goDll = raw.loadDll("/.go/TestSlice.dll",,"cdecl");

//创建 Go 切片
import golang.slice;
var slice = golang.slice({

    //指定原生数组，字段名必须�?value，[]表示动态长�?    int value[] = {23,1,22} //动态数组不能为空数�?})

//调用 Go 函数
goDll.TestSlice(slice);

/*
如果 Go 代码里修改了切片�?那么在调用后应尽快访问一�?value 字段 �?golang.slice 内部就会重新指向 aardio 分配的内存�?*/
var items = slice.value

//返回的值是一个普�?aardio 数组�?console.dumpJson(items)

//slice 也可以直接转换为 JSON
console.dumpJson(slice)

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Go/slice.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Go/slice.md')

