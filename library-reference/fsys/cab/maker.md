[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# fsys.cab.maker 库模块帮助文�?
## fsys.cab.maker 成员列表

### fsys.cab.maker.compress(待压缩目录或文件,输出目录,"MSZIP")

压缩文件名目录（路径不能包含Unicode 字符），生成 cab 文件�?
支持嵌套子目�?
参数 @2 ,参数 @3 可省�?默认使用 LZX 算法(压缩率较�?.

成功返回 true,失败返回 null,错误信息

### fsys.cab.maker.logger

指定压缩进度默认回显对象

该对象必须有 log �?write 成员函数用于输出信息

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/fsys/cab/maker.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/fsys/cab/maker.md')

