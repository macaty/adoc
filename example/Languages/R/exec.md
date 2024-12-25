[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 执行 R 语言代码

```aardio aardio
//aardio 执行 R 语言代码
import console;
import process.r;

//可自定义 Rscript.exe 路径，不指定则自动获�?//process.r.setScriptPath("C:\Program Files\R\R-4.2.0\bin\x64\Rscript.exe")
//教程: https://mp.weixin.qq.com/s/QSJUraefFctJYN_cudesZw

//执行�?R 代码，参�?@1 可以指定 R代码�?R 文件�?var out = process.r.exec(`
args=commandArgs(T);
write(args[1],file=".data.txt");

# list 有点�?aardio 中的�?table)，可以包含各种数据类型，
a <- list(hello = 1, world = "字符�? ) # <- 相当�?aardio 中的等号,  R的等号一般用于分隔键值对
print ( a[["world"]] ); # aardio 里的直接下标也是这么�?print ( a$world ); # 相当�?aardio 里的  a.world
print ( a[1] ); # 这个返回的是键值对 hello = 1，不�?aadio �?a[1] �?a.hello 是指向不同的元素�?print ( mode(a[1]) ); # 数据类型还是显示�?list

b <- TRUE #布尔值必须全大写
print( b )

# 向量
a = c(10, 20, 30, 40, 50)
print( a[1] ) #起始下标�?1 ,这跟 aardio 一�?print( a[1:4] ) # 取出�?1 项到�?4 �?
# 定义函数，与 aardio 语法类似
new.function <- function(a,b,c) {
   result <- a * b + c # 类似 aardio 中的 return a * b + c #
   print(result) # 指定返回值以后，还能继续执行后面的代码，不像 aardio 函数 return 后面的代码被忽略�?}

print( new.function(2,3,1) )
`,"测试一�?); //可以添加不定个数的启动参�?console.log( out );

console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/R/exec.md)

