[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# COM 对象 - 实现接口

参�? [COM基础知识](base.html)

## com.ImplInterface

1. 函数原型�?
   `interface = com.ImplInterface( table对象,ProgID,接口名字 )`

2. 函数说明�?
   函数将指定的 table 创建为指定的 com 接口.

3. 调用示例�?

   ```aardio aardio
   var ocxEvents2 = {
     MediaChange = function(item) {
       winform.edit.print("ocxEvents2.MediaChange",item.sourceURL)
     }
   }
   var eventSink =  com.ImplInterface(ocxEvents2,"WMPlayer.OCX.7","_WMPOCXEvents")

   ```


## 创建 IDispatch 接口对象

在调�?COM 对象的函数时，table 参数可以自动转换�?IDispatch 接口对象�?
所以需要手动调�?com.ImplInterface �?table 对象转换IDispatch 接口对象的情况并不多见�?
1. 函数原型�?
   `dispatch = com.ImplInterface( table对象 | 函数对象 )`

2. 函数说明�?
   如果指定一个函数对象作为参数，则仅支持使用匿名 DISPID 进行 Invoke 调用,DISPID 将会传递给函数�?owner 参数.

   如果指定一�?table 对象作为参数，则可使�?IDispatch 接口自动公开 table 对象的命名成员。而被调用成员函数�?owner 参数将会�?table 对象自身(而不�?DISPID ) �?
   也可以在表对象中指定小于 0 �?DISPID 作为成员的数值键以支持匿�?DISPID 调用。在查询 DISPID 时，aardio 将使�?[直接下标](../../../language-reference/operator/member-access.html)(不会触发元方�?�?
3. 函数示例�?

   ```aardio aardio
   import com;
   import console;

   var dispatch = {

     [ -5/*_DISPID_EVALUATE*/ ] = function(...){

     }

   }

   //实际 COM 接口
   var dispatchObject = com.ImplInterface(dispatch);

   console.log( dispatchObject(123) );
   console.pause();

   ```


   �?IDispatch 接口对象中可使用 [\_call 元方法](../../../language-reference/datatype/table/meta.html#_call) 定义 COM 默认调用，使�?[\_item 元方法](../../../language-reference/datatype/table/meta.html#_item) 定义 COM 枚举表或 COM 默认调用表�?

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-guide/builtin/com/ImplInterface.md)

