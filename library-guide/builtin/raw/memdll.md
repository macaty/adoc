[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# 内存 DLL

aardio 可以直接从字符串加载内存DLL模块�?
注意不是所�?DLL 组件都支持内存加载�?越简单、独立无依赖�?DLL 越容易内存加载�?�?aardio 中使�?tcc 扩展库调�?�?C 语言编译�?DLL 一般都可以内存加载�?Go 语言开发的 DLL 通常可以内存加载，但应指定多线程共享名称以避免重复加载�?
加载内存 DLL 的语法如下：

```aardio aardio
var memDll = raw.loadDll(DLL内存数据,线程共享�?调用约定)

```

参数 @1 可指定一�?DLL 文件路径，并�?DLL 文件路径前添加包含操作符 `$` �?以实现在编译时将 `$` 操作符后面指定的 DLL 文件编译为二进制字符串（编译或发布后不在需要源 DLL 文件）， 并在运行时加载为内存数据�?
如果指定"线程共享�?，则多线程加载时可以共享已加载的内存 DLL 模块�?
如果指定线程共享名时可省略参数@1 —�?表示仅查找并返回已加载的内存DLL�?
否则必须指定参数@1，调用约定参数可省略�?
注意"线程共享�?虽然是可选参数，但通常不应该省略此参数。有一�?DLL 在同一个进程中加载多个内存 DLL 模块时可能会出现一些奇怪的问题�?这时候指�?线程共享�?参数以实现跨线程共享同一个内�?DLL 模块可以解决这类问题�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-guide/builtin/raw/memdll.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-guide/builtin/raw/memdll.md')
