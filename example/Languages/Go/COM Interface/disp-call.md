[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 Go 语言 - 调用 COM 接口 DLL

```aardio aardio
//aardio 调用 Go 语言 - 调用 COM 接口 DLL
import console.int;
console.open();

//内存加载 DLL，请先编�?Go 代码生成 DLL
var dll = raw.loadDll($"/dispDemo.dll",,"cdecl");

//aardio 对象转换�?COM 对象（COM 接口会自动转换，原生 DLL 接口要调�?com.ImplInterface �?import com;
var disp = com.ImplInterface(
    //任意表对象或函数都可以转换为 COM 对象（IDispatch 接口对象�?    Add = function(a,b){

        console.log("Add 函数�?Go 语言调用�?);
        return a + b;
    }
);

//调用 Go 函数
var pDisp = dll.TestDispatchP(disp);

//�?Go 函数返回�?IDispatch 指针转换�?COM 对象
var comObj = com.QueryObjectR(pDisp);//转换同时释放一次引用计�?
//操作 COM 对象
comObj.Add("key","value");
comObj.Add("key2","value2");

//遍历 COM 对象
for index,key in com.each(comObj) {
    //输出字典的键�?    console.log( key,comObj.Item(key) )
}

console.log(ptr)

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Go/COM Interface/disp-call.md)

