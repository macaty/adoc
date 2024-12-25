[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# sys.font 库模块帮助文�?
## sys.font 成员列表

用于安装或检查系统字体�?
相关库：win.font,gdi,gdip.family,fonts

### sys.font.exist()

检测指定的字体是否可用，参�?@1 指定字体名称�?
支持系统安装的字体，以及仅添加到当前进程的字�?
### sys.font.getLink()

返回链接字体配置，参数指定字体名�?
### sys.font.getName(fontname,langId)

参数 @fontname 指定字体名，

返回该字体由 @langId 参数指定语言 ID 的字体名称�?
简体中文语言 ID �?0x804，英文为 0x409，默认为 0x409

### sys.font.install()

安装系统字体，参数@1指定字体路径�?
参数 @2 �?true 为所有用户安装字体（重新登录系统生效），进程需要管理权限�?
否则字体安装�?%LOCALAPPDATA%\\Microsoft\\Windows\\Fonts\ 目录，仅对当前用户生效�?
如果希望添加的字体仅对当前进程有效，可以改用 win.font.add 函数

### sys.font.open()

打开字体文件�?
### sys.font.setLink(fontName,value)

修改链接字体配置，注销并重登录操作系统后生效�?
参数@1指定字体名称�?
参数@2可传入字符串数组，也可以传入一个多行字符串

注意链接字体必须是为所有用户安装的系统字体�?
也就是安装到 C:\\Windows\\Fonts 目录下的字体�?
可以调用 sys.font.install 函数安装字体到该目录

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/sys/font.md)

