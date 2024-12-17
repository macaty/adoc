[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 VBA/JSA 操作 Excel

```aardio aardio
//aardio 调用 VBA/JSA 操作 Excel
import console.int;
import com.excel;

//打开或创�?Excel 文件，xlsm 格式支持宏（ VBA / JSA ）�?var xl = com.excel("/vba.xlsm");

//自由调用 VBA / JSA 函数，不需要确认启用宏�?var data = xl.vba.GetSheetData();//先用 VBA 编写函数，宏管理器能看到函数名�?
/*
自动支持 VBA 数组，不需要任何其他封装�?数组是值类型，操作数组不用再返�?VBA 进程，相对来说简单高效�?*/
console.dumpJson(data);

/*
VBA 也可以自由调�?aardio 对象�?所�?aardio 对象都支�?VBA 迭代For Each �?Next 语句�?
�?VBA 可以调用 aardio 对象的属性、函数�?�?VBA  动态读写属性要这样写：
CallByName (aardioObject, "读取属性名", vbGet)
CallByName aardioObject, "写入属性名", VbSet, "属性�?
*/
xl.vba.CallAnything({
    //�?Excel �?WPS 表格中按 ALT + F11 打开代码窗口�?    //VBA 编辑器会自动将某些函数名转为大写，aardio 是区分大小写的�?    Log = function(str){

        console.log("VBA调用任意 aardio 函数，参数：",str);

        //owner 表示当前拥有 Log 函数的对象自�?        console.log(owner.Name)
    };

    Name = "aardio";
});

/*
VBA,JSA 源码可打开 /vba.xlsm 查看代码�?
JSA 调用 aardio 对象的成员函数要这样写：
aardioObject.Invoke("Log","这是来自 JSA 的参数�?);
�?VBA 可以直接�?aardioObject.Log("这是来自 JSA 的参数�?)

JSA 里读�?aardio 对象属�?aardioObject.Invoke_Get("属性名");
aardioObject.Invoke_Set("属性名","属性�?);

另外 aardio 里可以用
web.json.stringify( value ) 将对象转换为 JSON�?也可以用 web.json.parse( json ) 方便地解�?JSON 为对象�?
�?JS 使用 JSON.stringify( value ) 生成 JSON�?使用 JSON.parse 解析 JSON�?
使用 JSON 交互数据也是很方便的�?
�?aardio 里调�?JSA 代码中可以可以插�?debugger; 语句�?WPS 遇到 debugger; 会自动跳出调试工具�?*/

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/VBA JSA/Excel.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/VBA JSA/Excel.md')

