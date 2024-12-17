[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# 断言函数

## 一�?assert 函数

函数原型:

`assert(value,message,...)`

assert 断言第一个参�?@value ，如果第一个参数为真则将所有参数作为返回值返回。如果第一个参数为假，则将第二个参�?@message 作为异常抛出�?
在aardio 里很多函数都支持 assert ，如果执行成功第一个值返回一个真值�?如果执行失败则返回两个参数，第一个为 false �?null ，而第二个返回值为错误信息。这恰好符合 assert 断言函数的逻辑�?
例如�?
`var func = assert( loadcode("\notfound.aardio") );`

loadcode 如果执行成功，assert 将返回值顺利的传递给 func�?loadcode 如果执行失败，第一个返回值为null，第二个返回值为错误信息，则导致 assert 断言失败并抛出错误信息�?
## 二�?assert2 函数

函数原型:

`assert2(level,value,message,...)`

参数 @value 为真则返回其他�?否则将参�?@message 作为异常抛出。参�?@level 指定抛出异常的调用级别，2 为调用�?1 为当前函数�?
assert2 �?assert 函数的用法与作用是一样的，唯一的区别是 assert2 可以在首个参参数中指定抛出异常的调用栈级别�?
## 三�?assertf 函数

函数原型:

`assertf(condition,value,...)`

assertf 的作用与 assert 基本相似，但是断言逻辑是完全相反的。assertf 要求第一个参�?@condition 必须�?false(false,0或null)，如果为�?true,非零值，非null�?，则将第二个参数 @value 作为异常抛出。如果第一个参数为�?断言成功)，则返回该参数之后的其他参数�?
assertf �?assert 有以下区别：

- assert 断言第一个参数必须为真，assertf断言第一个参数必须为假�?- assert成功返回第一个参数（以及之后的其他参数），assertf 成功返回第二个参数（以及之后的其他参数）�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/language-reference/builtin-function/assert.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/language-reference/builtin-function/assert.md')

