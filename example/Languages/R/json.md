[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 R 语言 - JSON

```aardio aardio
//aardio 调用 R 语言 - JSON
import console;
import process.r;

//安装 R 包，如果已安装忽略不操作
process.r.require("jsonlite")

//如果返回值为 JSON，则自动解析 JSON 并返回对象�? var obj = process.r.json( `
library("jsonlite") # 载入 jsonlite �?
args <- commandArgs(T);
tab <- fromJSON(args[1], simplifyVector=FALSE,simplifyDataFrame=TRUE);

#不要�?print ，cat 不会加一堆不必要的东�?cat( toJSON(tab,auto_unbox=TRUE) )
`, {
  name1 = "测试一下，传对象给 R 语言";
  name2 = "这是一�?aardio 对象"
})

console.dumpJson(obj);
console.pause();

/*
https://cran.r-project.org/web/packages/jsonlite/jsonlite.pdf
https://cran.r-project.org/web/packages/jsonlite/vignettes/json-aaquickstart.html

R 里面单个值是原子向量，相当于别的语言里长度为 1 的数组�?正常的单个值传�?R，给 R �?jsonlite 转来转去就变成了 1 个元素的数组�?
要避免这个问题，toJSON 要加�?auto_unbox=TRUE 参数以自动解包为单个值�?jsonlite 提供 unbox 函数，不�?unbox 用到非原子向量就会报错，所以还是用 auto_unbox�?
如果 toJSON 设置�?auto_unbox=TRUE �?那么 fromJSON 就要设置 simplifyVector=FALSE 以避免将长度�?1 的数组转换为原子向量�?因为原子向量会被 unbox 为单个元素，要避免长度为 1的数组被 unbox 为单个值�?
simplifyDataFrame=TRUE 是指将符合条件的对象数组自动转换�?R 的数据帧�?*/

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/R/json.md)

