[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# call() 函数

call() 函数用于调用一�?aardio 函数,并可自定�?owner 对象，并获取错误信息

1. 函数原型�?
   `返回�?错误信息 = call(函数,owner,其他参数 ... )`

2. 函数说明�?
   call 函数可以调用并执行一个函数对�?


   与普通函数调用不同的�?可显式指�?owner 对象,并可获取错误信息而不是直接抛出异�?

3. 调用示例�?

   ```aardio aardio
   import console;

   var ok = call(console.log,console,123)

   var ok,err = call(notfound,console,123)
   if(!ok) console.log("出错�?,err)

   console.pause();

   ```


[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/language-reference/builtin-function/call.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/language-reference/builtin-function/call.md')

