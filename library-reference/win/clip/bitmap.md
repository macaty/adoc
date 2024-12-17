[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# win.clip.bitmap 库模块帮助文�?
## win.clip.bitmap 成员列表

剪贴板图像操作函数库

### win.clip.bitmap.read()

读取剪贴板图像并返回 gdip.bitmap 对象�?
可读取剪贴板中的位图、png、非远程 HTML 图像�?
[返回对象:gdipbitmapObject](../../gdip/bitmap.html#gdipbitmapObject)

### win.clip.bitmap.readDataUrl()

读取剪贴板图像并转换并返回为 Data URL 格式字符串�?
### win.clip.bitmap.readMarkdown()

读取剪贴板图像并转换�?Data URL�?
然后再转换并返回�?Markdown 格式字符�?�?
### win.clip.bitmap.test()

如果剪贴板图像有可读取的图像则返�?true;

### win.clip.bitmap.write

写入位图到剪贴板�?
### win.clip.bitmap.write(..)

用一个或多个参数指定 gdip.bitmap 构造参数�?
支持的参数与 gdip.bitmap 相同，请参�?gdip.bitmap 文档�?
### win.clip.bitmap.write(bmp)

参数 @bmp 指定 gdip.bitmap 对象�?
### win.clip.bitmap.write(图像文件路径或数�?

复制位图到剪贴板�?
如果事先导入标准�?inet.http,这里也可以直接传入图像网址�?
### win.clip.bitmap.writePng

写入 PNG 图像到剪贴板�?
### win.clip.bitmap.writePng(..)

用一个或多个参数指定 gdip.bitmap 构造参数�?
支持的参数与 gdip.bitmap 相同，请参�?gdip.bitmap 文档�?
### win.clip.bitmap.writePng(bmp)

参数 @bmp 指定 gdip.bitmap 对象�?
### win.clip.bitmap.writePng(图像文件路径或数�?

复制位图到剪贴板�?
如果事先导入标准�?inet.http,这里也可以直接传入图像网址�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/win/clip/bitmap.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/win/clip/bitmap.md')

