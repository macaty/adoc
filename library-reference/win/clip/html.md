[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# win.clip.html 库模块帮助文�?
## win.clip.html 成员列表

剪贴板HTML操作

### win.clip.html.format

注册�?CF\_HTML 图像格式，数值�?
### win.clip.html.test()

如果剪贴析包�?HTML 格式数据返回 true

## win.clip 成员列表

### win.clip.html()

创建剪贴板HTML对象

[返回对象:winClipHtmlObject](#winClipHtmlObject)

## winClipHtmlObject 成员列表

### winClipHtmlObject.ClipboardData

剪贴板数�?UTF8编码

该属性在解析剪贴板数据时自动生成,不要修改该属�?
### winClipHtmlObject.EndFragment

复制的片段结束位�?
该属性在解析剪贴板数据时自动生成,不要修改该属�?
### winClipHtmlObject.EndHTML

HTML 结束位置�?
不要修改该属�?
### winClipHtmlObject.StartFragment

复制的片段开始位�?
该属性在解析剪贴板数据时自动生成,不要修改该属�?
### winClipHtmlObject.StartHTML

HTML 开始位置，

该属性在解析剪贴板数据时自动生成,不要修改该属�?
### winClipHtmlObject.fragment

自剪贴板读取或写入的 HTML 代码中需要复制的片段，由其他函数自动设置�?
不要修改此属性�?
### winClipHtmlObject.html

自剪贴板读取或写入的 HTML 代码，由其他函数自动设置�?
不要修改此属性�?
### winClipHtmlObject.parse()

[返回对象:winClipHtmlObject](#winClipHtmlObject)

### winClipHtmlObject.parse(剪贴板数�?是否UTF8)

解析剪贴板数�?

参数@2默认为true,注意HTML在剪贴板为UTF8编码

成功返回对象自身

### winClipHtmlObject.read()

读取并解析剪贴板 HTML�?
成功返回对象自身�?
通过对象�?html,fragment 获取读取�?HTML 代码�?
[返回对象:winClipHtmlObject](#winClipHtmlObject)

### winClipHtmlObject.stringify(HTML,是否UTF8)

参数@1如果省略则获取对象的html或fragment属性生成复制数�?

成功返回可写入剪贴板的数�?
### winClipHtmlObject.write(剪贴板数�?是否UTF8)

参数@1如果省略则获取对象的html或fragment属性生成复制数�?

可选使用参数@3指定在复制前是否清空剪贴�?默认清空,

成功返回剪贴板数据句�?
[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/win/clip/html.md)

