[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 交互调用

```aardio aardio
//交互调用
import console.int;
import com.matlab;

//创建 MATLAB 应用
var m = com.matlab(true);

//------------------ 调用 MATLAB 函数 ------------------------------

//调用 MATLAB 函数，第一个参数指定有 3 个返回�?var dir,fname,ext =  m.fileparts(3,"c:\aardio\matlab.m" );

//如果首个参数不是数值，则可不指定返回值数量（默认设为 1）�?var result =  m.strcat("hello","world" )

//------------------ 执行命名或表达式 ------------------------------

//执行绘图命令
m.exec("plot(1:10)")

//解析下标中的 MATLAB 表达式�?var data = m[`{'one'; 'two'; 'three'}`]

//------------------ 读写工作区变�?------------------------------

//读写 base 工作区的变量
m.base.varname = "测试字符�?base 工作区�?;

//读写 globa 工作区的变量
m.global.varname = "global 工作�?;

//批量写入变量到工作区
m.base.assign({
    var1 = 1;
    var2 = 2;
    var3 = 3;
})

//----------------------- 读写矩阵 -------------------------------

var realPart = { {1,2}, {3,4} }
var imagPart = { {1,0}, {0,2} }

//写入矩阵�?base 工作�?m.base.putMatrix("B", realPart, imagPart)

//�?base 工作区读取矩�?var realPart,imagPart =   m.base.getMatrix("B" )

//回显结果
console.dumpJson(realPart );
console.dumpJson(imagPart );

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/MATLAB/matlab.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/MATLAB/matlab.md')

