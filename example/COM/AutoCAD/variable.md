[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 AutoCAD - 读写系统变量

```aardio aardio
//aardio 调用 AutoCAD - 读写系统变量
import com.cad;
var cad = com.cad();
cad.Visible = true; //是否显示 AutoCAD 窗口

try{

    //读取系统变量
    var secureLoad = doc.GetVariable("SECURELOAD");

    /*
    设置系统变量，要特别注意值的类型要非常准确，不然会报错�?    VBA里的 Integer 类型 0 �?aardio 中要写为 com.word(0)，千万别搞错写为 com.int(0)
    VBA里的 Double  类型 0 �?aardio 中要写为 com.double(0)

    要注意在 aardio �?COM 参数不声明类型时�?    单个整数值默认在 COM 函数中会转为 4 字节 VT_I4( int ) 类型变体，而小数值默认转�?8 字节 _VT_R8（double) 类型变体�?    纯数值数组会转为 _VT_R8（double) 类型 SAFEARRAY，要特别注意这里没有使用整型�?
    细节请参考「aardio 范例 / COM 组件 / 进阶提示 / 参数类型转换�?    */

    doc.SetVariable("SECURELOAD",com.word(0));

}
catch(e){
    //读写 AutoCAD 版本不支持的系统变量会报�?}

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/COM/AutoCAD/variable.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/COM/AutoCAD/variable.md')

