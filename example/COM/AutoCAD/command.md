[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 AutoCAD - 加载 LISP 代码

```aardio aardio
//aardio 调用 AutoCAD - 加载 LISP 代码
import com.cad;
var cad = com.cad();
cad.ShowForeground();//前置并显示窗�?
//加载 LISP 代码或�?LSP 文件�?//支持模板语法�?https://www.aardio.com/zh-cn/doc/language-reference/templating/syntax.html
cad.LoadLisp(`
(setq c:hello nil)
(defun c:hello(/ name)
(set 'name (getstring "What's your name? "))
(set 'msg (strcat "Hello, " name <?=

    /*
    支持模板语法: https://www.aardio.com/zh-cn/doc/language-reference/templating/syntax.html

    LISP 模板�?com.cad.loadcode() 函数解析�?    转换规则如下�?
    一、如�?aardio 输出非空数组或多个参�?�?        所有参数按以下规则转换为字符串�?
        1、数值直接输输出，flase 转为 nil ，true 转为 T
        2、数组或嵌套的数组参数都会转换为 LISP 表（首尾有括号）�?           如果 cons 字段�?true 则转换为点对（首尾有括号）�?        3、包�?car,cdr 成员的表会转换为点对（首尾有括号）�?           其他名值对转换为关联列表�?        4、其他类型统一调用 tostring() 转换为字符串�?        然后�?LISP 语法进行转义，首尾加双引号�?
        最后将所有参数以空格分开输出�?LISP 代码（首尾不加括号）

    二、单个表参数为包�?car,cdr 成员的表会转换为点对（首尾有括号）�?        如果表参数为其他名值对则转换为关联列表（首尾有括号�?
    三、其他单个参数直接转为字符串并置�?LISP 代码�?    */
    tostring(time()),"这是 aardio 对象"
?>))
(write-line msg))`,/*可选用 参数@2 指定模板 owner 参数*/);

//执行 AutoCAD 里所有命令以�?AutoLISP 表达式，跟在 AutoCAD 里敲命令效果一样�?cad.SendCommand("hello");

//cad.SendCommand 同样支持模板语法�?//aardio 表转 LISP 点对，首尾自动加括号
//cad.SendCommand(`(print '<?= { car = "点对 car"; cdr = "点对 cdr" } ?> )` );

//aardio 数组输出�?LISP 列表，首尾不会自动加括号
//cad.SendCommand(`(print '(<?= {1,2,3,{"嵌套"}} ?>) )` );

/*
cad.SendCommand 是同步执行命令，
如果要异步执行命令请使用 cad.PostCommand
*/

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/COM/AutoCAD/command.md)

