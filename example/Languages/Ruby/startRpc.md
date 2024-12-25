[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 Ruby 函数

```aardio aardio
//调用 Ruby 函数
import console.int;
import process.ruby;

var code  = /*

#可加载应用程序目录下的其他代码文�?#load "test.rb"

#定义 Ruby 函数
def add(a, b)
  a + b
end
*/

//启动 Ruby RPC 服务端，这样就不用重复启�?Ruby，速度更快
var ruby,err = process.ruby.startRpc( code )

//调用 Ruby 函数
var ret,err  = ruby.add(2,3)

//获取返回�?ret = ret[["result"]]
console.dump(ret);

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Ruby/startRpc.md)

