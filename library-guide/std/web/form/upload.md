[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# 自动上传文件

构造上传文件的表单数据较复�?标准库提供了 web.multipartFormData 类可以自动构造上传文件表单的数据包�?
## web.multipartFormData

1. 语法�?

   ```aardio aardio
   import web.multipartFormData;
   var form = web.multipartFormData();
   form.add("字段�?,"字段�?)
   form.add("上传字段�?,"@上传路径");

   ```

2. 说明�?
   web.multipartFormData是一个类,创建的表单对象可以使用add(字段�?段�?函数添加上传数据，字段名指网页表单中输入控件的名�?该控件html源码中的name属�?，可添加多个字段,如果该字段的值第一个字符是"@"字符则上传该文件。在标准�?web.rest.client中有上传文疾糠州有用�?web.multipartFormData 可以参考一下源码�?
3. 示例�?

   ```aardio aardio
   import web.form;
   /*DSG{{*/
   var winform = ..win.form( text="自动上传";right=744;bottom=523 )
   /*}}*/

   var wb = web.form( winform ); //创建 Web 窗体
   winform.show();

   //构建上传数据�?   import web.multipartFormData;
   var formData = web.multipartFormData();
   formData.add("username","用户�?);
   formData.add("password","密码");
   formData.add("filename","@\main.aardio");

   //上传数据
   wb.post("http://httpbin.org/post"
   , formData.readAll() //上传数据�?   , formData.contentHeader()  //要添加的HTTP�?   );

   //启动消息循环
   win.loopMessage();

   ```


[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-guide/std/web/form/upload.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-guide/std/web/form/upload.md')

