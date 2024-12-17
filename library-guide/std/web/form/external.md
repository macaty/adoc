[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# 在网页中调用 aardio 代码

参�? [创建 Web 窗体](webform.html) [在aardio中执行网页脚本](doScript.html)

## wb.external

1. 接口语法�?

   ```aardio aardio
   wb.external = {
     成员名字 = �?   }

   ```

2. 函数说明�?
   定义 wb.external 为一�?table 对象,然后我们可以在网页脚本中直接访问 external 对象�?
   aardio 要求你显示的指定 external 以及 external 的成�?是需要你基于本机安全去考虑哪些方法应当公开给网页访问�?
3. 调用示例�?

   ```aardio aardio
   //....省略创建 Web 窗体的代�?
   //创建 external 接口
   wb.external = {
     //可以通过javascript脚本访问external接口的所有成�?     aardio_func = function( arg ){
        win.msgbox("我被网页上的脚本调用�? + arg + "
        aardio的语法与Javascript很接近哦" )
     }
   }

   //在网页上执行 javascript 脚本
   wb.doScript("javascript:external.aardio_func(123);")

   ```

4. 调用示例�?

   ```aardio aardio
   //....省略创建 Web 窗体的代�?
   //只要�?Web 窗体external内的成员，都可以从网页上调用
   wb.external = {
     showmsg = function (txt){
        win.msgbox(txt, "aardio");
        return true;
     }
   }

   //在网页的 JavaScript 里可以直接调�?external 成员
   wb.write( "
   <button onclick='external.showmsg(123)' >我是网页上的按钮</button>
   " )

   ```


   external 使用的是 IDispatch 接口,请参�? [创建IDispatch接口](../../../builtin/com/ImplInterface.html#IDispatch)


[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-guide/std/web/form/external.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-guide/std/web/form/external.md')

