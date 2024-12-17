[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 AutoCAD LISP 函数

```aardio aardio
//aardio 调用 AutoCAD LISP 函数
import win;
import com.cad;

var cad = com.cad();
cad.ShowForeground();

//获取 Lisp 函数�?var lisp = cad.GetLispFunctions();
//AutoCAD 提供的这个接口不是太稳定，调用某些函数偶尔会出现异常（似乎不用绘图函数就行）�?
//用这个接口必须用 vl-cmdf 替代 command 调用命令�?lisp.vl.cmdf("commandline")

//调用 LISP 函数
var path = lisp.getFiled("打开文件:", "./", "*", 8);

//调用 LISP 函数
lisp.print(

    /*
    lisp 自身可作为生�?LISP 表达式的函数调用�?    可将 aardio 数组或点对表转换�?LISP 表达式�?    */
    lisp( {
        {car=12,cdr=23},//LISP 点对
        {1,2,3,path},//LISP 列表
        {name="Tom",age=23},//LISP 关联列表
        "来自 aardio  代码的字符串",
        123,
        false,
        true
    } )
);

//这样写也可以
lisp.print(
    lisp(`((1,2,3) (4 5 6 7 8 9))`)
);

//执行 LISP 表达式（此接口基�?cad.GetLispFunctions，限制同�?�?cad.LispExp(`(print '(<?= {1,2,3,{"嵌套"}} ?>) )` );
/*
cad.LispExp 支持模板语法:
https://www.aardio.com/zh-cn/doc/language-reference/templating/syntax.html

LISP 模板�?com.cad.loadcode() 函数解析�?转换规则如下�?
一、如�?aardio 输出非空数组或多个参�?�?    所有参数按以下规则转换为字符串�?
    1、数值直接输输出，flase 转为 nil ，true 转为 T
    2、数组或嵌套的数组参数都会转换为 LISP 表（首尾有括号）�?        如果 cons 字段�?true 则转换为点对（首尾有括号）�?    3、包�?car,cdr 成员的表会转换为点对（首尾有括号）�?        其他名值对转换为关联列表�?    4、其他类型统一调用 tostring() 转换为字符串�?    然后�?LISP 语法进行转义，首尾加双引号�?
    最后将所有参数以空格分开输出�?LISP 代码（首尾不加括号）

二、单个表参数为包�?car,cdr 成员的表会转换为点对（首尾有括号）�?    如果表参数为其他名值对则转换为关联列表（首尾有括号�?
三、其他单个参数直接转为字符串并置�?LISP 代码�?*/

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/COM/AutoCAD/vla.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/COM/AutoCAD/vla.md')

