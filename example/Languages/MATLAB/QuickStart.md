[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 入门

```aardio aardio
//入门
import console.int;
import com.matlab;

//创建 MATLAB 应用程序
var m = com.matlab(true);

//批量写入变量�?base 工作�?m.base.assign({
    var1 = 1;
    var2 = 2;
    var3 = 3;
})

//执行代码，支持用模板语法嵌入 aardio 代码和对�?m.code = /*

var5 = <?
    //�?MATLAB 代码中直接写 aardio 代码�?    ={ 1,2,3 }
?>
*/

//调用 MATLAB 函数
var result =  m.strcat("hello",",world" );
console.log(result);

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/MATLAB/QuickStart.md)

