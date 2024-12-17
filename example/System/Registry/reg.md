[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 注册表操�?- 入门

```aardio aardio
//注册表操�?- 入门
import console;

//sys.reg 的代码只有几句，提供简单的写注册表功能
import sys.reg;

//写注册表，根键不用指定，默认�?HKEY_CURRENT_USER
sys.reg.setValue("�?,"�?,"Software\aardio\test.aardio.code")

//win.reg 提供更多的读写注册表功能
import win.reg;

//创建新的注册表路�?var reg = win.reg("HKEY_CURRENT_USER\Software\aardio\test.aardio.code")
console.log(reg.queryValue("�?)); //读注册表�?
reg.renameKey("test.aardio.code.new"); //修改键名
reg.setDwValue("testaaa",123); //设置新�?reg.delValue("testaaa"); //删除指定的�?reg.save("/backup.bin"); //导出注册�?reg.load("/backup.bin"); //导入注册�?reg.close();

reg = win.reg("HKEY_CURRENT_USER\Software\aardio\");
reg.delKey("test.aardio.code.new"); //删除�?
//仅打开已存在的路径
var reg = win.reg("HKEY_CURRENT_USER\Software\aardio\",true);

//枚举子项、以及子项的所有子�?reg.enumKey(

    function(
        subKey, /*这是某个子节�?win.reg对象)*/
        keyname/*这是reg子节点的一个子项的名字*/
    ){
        console.log(keyname)
    }
)

reg.close();
execute("pause")

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/System/Registry/reg.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/System/Registry/reg.md')

