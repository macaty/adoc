[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 嵌入式调 PHP - 语法比较

```aardio aardio
//aardio 嵌入式调 PHP - 语法比较
import php;
import console;

php.print = function( msg ) {
    console.log("echo:", msg)
}

//PHP代码
phpcode =/***

    //echo语句类似aardio中的 io.print
    echo "PHP的注释语法与aardio一�?语句也以分号结束,并且分号不能象aardio那样省略\n";
    echo 'PHP 中的所有变量必须以 $ 符号开始�?$号是变量的修饰前缀,但不是变量名称的一部分';
    echo "在PHP中函数内部变量默认为局部变�?这与aardio,Javascript正好相反),使用 global 语句引入或声明全局变量\n";
    global $g; //定义全局变量
    $abc = 123; //定义局部变�?
    $str = "hello"." World"; //PHP连接字符串使用圆�?类似aardio中的 ++ 操作�?
    /*
        创建关键数组,类似aardio中的表：
        var arr = { a = 123; b = "字符�?}
        其他编程语言多使用逗号分隔数组成员,
        但aardio使用分号分隔表成员�?    */

    $arr = array(
        //注意键名放在字符串中,aardio中等价的写法是{ a = 123;} �?{ ["a"] = 123 }
        "a" => 123,
        "b" => "字符�?
    );

    /*
        遍历数组,在aardio中等价的语句�?
        for(k,v in arr){
            io.print("a[" + k + "] = " + v )
        }

        aardio的迭代语句是 for( 成员变量�?in 数组�?){ }
        而PHP的迭代语句是 for( 数组�?as 成员变量�?){ }
    */
    foreach ($arr as $k => $v) {
        echo "\$a[$k] => $v.\n"; //PHP双引号中的字符串可以直接使用变量
    }

    //访问数组成员类似aardio的索引语�?但PHP不支�?arr.b 这样的写�?    echo $arr["b"];

    /*
        explode()函数使用参数1指定的分隔符拆分字符串并返回数组�?
        aardio中等价的代码�?        var arr = string.split("a,b,c,d",",")

    */
    $arr = explode(",","a,b,c,d");
    foreach ($arr as $k => $v) {
        echo "\$a[$k] => $v.\n"; //PHP双引号中的字符串可以直接使用变量
    }

    /*
        PHP早期不支持名字空�?数组函数多以 array为前缀
        而aardio中数组相关函数都在table名字空间下�?
        例如数组替入,在aardio中使�?table.splice() 函数
        在PHP中使�?array_splice() 函数,用法大同小异�?        array_splice() 替入的是一个数�?�?table.splice() 替入不定个数的参�?    */
    array_splice($arr,2,1,array("d","e") );
    foreach ($arr as $k => $v) {
        echo "array_splice \$a[$k] => $v.\n"; //PHP双引号中的字符串可以直接使用变量
    }

     /*
        PHP里创建类

        aardio里不同的是：
        1. 类成员必须写成键值对格式,函数也一�?例如 member_func = function(){ };
        2. 私有成员必须写在构造函数里用var语句声明为类作用域局部变�?PHP里的var语句则是公开成员,语义相反
     */
    class Cart{
        //定义成员变量,
        /*
            PHP里var可不是定义局部变量的意思�?            PHP5里var实际上是public的别�?一般使用public.

            而在aardio里类的所有成员变量默认就是公开�?也就是public�?
            aardio里没有public等价的关键字,与javascript类似,aardio中使用var语句声明局部变量�?            在类的构造函数中用var语句就可以声明类作用域有效的私有成员。所以var在aardio中的用意与PHP恰恰相反
        */
        var $items = 123; // 新的写法一般应改用public

        /*
            static定义静态成员变�?静态变量被类所有实例对象共享�?            在类外部访问静态成员的语法�?类名::静态成员变�?            类内部访问静态成员的语法�?self::静态成员变�?
            aardio对应的是类的名字空间,用self表示�?            在aardio�?变量的默认名字空间就是类的名字空间�?            也就是默认的变量就是静态变�?所以在类内部写 self.变量�? 与直接写变量名是等价的�?
            PHP用self表示�?�?this表示类当前创建的实例对象�?            这与aardio的这两个关键字语义类�?self表示�?在aardio中也即名字空�?,this表示当前创建的实例对象�?            不过aardio的成员操作符都是使用圆点,

            PHP�?self::静态变量名 在aardio中可以写 self.静态变量名
            PHP�?$this->实例变量�?在aardio中可以写 this.实例变量�?        */
        static $s_num = 456;

        /*
        PHP使用const定义常量(一般大�?,
        在类外部一般使�?类名::常量 的方式访�?类似静态变�?

        aardio则在成员变量前加一个加划线表示成员常量�?        类的名字空间、类的实例都可以使用这种常量�?        例如 self._const_name this._const_name 等等�?
        aardio的常量如果大�?表示全局有效的常�?
        例如 _CONST_NAME

        在很多语言中通常习惯性的为常量加上下划线前缀、全局常量通常大写,
        但这仅仅是书写习�?而在aardio中这个书写方式变成了定义常量的语法�?        */
        const CHARSET = "abc";

        // �?$num �?$artnr 放入车中
        function add_item ($artnr, $num){
            $this->items[$artnr] += $num;
        }

        // �?$num �?$artnr 从车中取�?
        function remove_item ($artnr, $num){
            if ($this->items[$artnr] > $num) {
                $this->items[$artnr] -= $num;
                return true;
            } else {
                return false;
            }
        }
    }

    /*
        创建类对象实�?        等价的aardio代码如下�?
        var a = Cart() // aardio创建类实例不需要使�?new关键�?        io.print( a.items )

        PHP访问对象成员不是使用圆点,而是使用C指针操作�?->
        因为圆点已经被用作字符串连接符了,以致于PHP新增的名字空间要用斜杠表示�?        PHP无论是语法、还是函数命名都略有些混�?这是PHP的一个遗憾�?    */
    $a = new Cart;
    echo $a->items;//注意这里items前面不能再加$符号
    echo Cart::CHARSET;

$str = <<<EOT

    php中heredoc语法很象aardio中用块注释表示字符串的语�?

    str = /**
        这是aardio类似heredoc的语�?    **/

    不同的是,aardio匹配块注释首尾标记的星号数目来确定边界�?    而PHP则在<<<符号后面指定结束标记�?
    结束标记一定要放在单独的一�?后面必须有分�?这一行不能有缩进,不能有空格�?    所以heredoc的语法非常严�?相对来说aardio的语法要简洁直观一�?
    heredoc中也可以直接置入PHP变量,例如:  $a->items
EOT;

***/

console.open();

//运行PHP代码,返回表达式的�?php.exec( phpcode );

console.log( php.str ); //取php变量,注意不要写美元符号前缀

console.pause();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/PHP/EmbedVM/embed.exec.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/PHP/EmbedVM/embed.exec.md')

