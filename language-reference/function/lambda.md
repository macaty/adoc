[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# lambda 表达�?
lambda 表达式用于定义匿名函数，与普通匿名函数的区别如下�?
1. lambda 不需要写 return 语句就可以直接返回一个表达式�?
   例如 `lambda() 123` 等价�?`function() return 123`�?
2. lambda 的函数体只能是一个表达式，不能使用其他语句或语句块，
   例如 `lambda(){}` 等价�?`function() return {}`

3. lambda 表达式不包含逗号，不会返回多个值�?
   例如 `console.log( lambda() 123, 456 )`
   等价�?`console.log( function() { return 123 }, 456 )`

4. lambda 表达式的函数体不是语句，不能包含分隔语句的分号�?
   例如 `console.log( lambda() 123; )` 是错误的写法，�?`console.log( function() return 123; );` 则是语法正确的写法（函数是语句，语句可以分号结束）�?
5. 不能�?lambda 表达式作为操作数，并直接在右侧写一元操作符（例如调用操作符）。例�?`lambda() 123()` 这样写是不对的，我们需要用括号�?lambda 转换为普通表达式，语法正确的写法�?`( lambda() 123 )()`�?
6. 可选使用希腊字�?λ 代替 lambda 关键字�?

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/language-reference/function/lambda.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/language-reference/function/lambda.md')

