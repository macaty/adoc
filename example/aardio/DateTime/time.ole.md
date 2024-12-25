[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: OLE时间对象

```aardio aardio
//OLE时间对象

import console;
import time.ole;

//我们试一下创建一个OLE时间对象
var tm = time.ole();

//给他1970年以前的时间
tm.year = 1932;

//正确出现数�?console.log(  tonumber( tm )  )

tm.year = 3010;//�?
//再把他转换回�?仍然正确显示年份
console.log( time.ole( tonumber( tm ) ) )

//OLE时间支持系统格式化语�?var str = tostring(tm,"yyyy-MM-dd HH:mm:ss")
console.dump(str)

//也默认支持time对象的格式化语法
console.log(tostring(tm,"%Y�?m�?d�?%H�?M�?S�?))

//还可以转换格式化语法
console.log( tm.toSystemFormat("%Y�?m�?d�?%H�?M�?S�?))

//time对象也支�?900年到9999年之间的时间
var tm = time("1969/1/1 11:21:03","%Y/%m/%d %H:%M:%S")
console.log(tm)

//但是数值运行就不支持了
console.log( tonumber(tm) )

console.pause()

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/aardio/DateTime/time.ole.md)

