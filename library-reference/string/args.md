[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# string.args 库模块帮助文�?
## string 成员列表

### string.args(args,dashCase,Separator,boolean)

可选用 @args 指定初始表参数�?
返回表转换为命令行时将默认调�?string.args.joinEx 函数�?
参数转义规则请参�?string.args.joinEx 函数�?
如果 @dashCase �?true（默认值），则�?/�? 前导符的参数�?
由小驼峰转为连字符风格并�?\-\- 前缀�?
名值对默认以空格分开�?
可用 @separator 参数自定义名值对分隔符，例如 = 号�?
如果 @boolean 参数恒等�?false�?
则布尔值为 true 的参数省略值，仅保留参数名�?
则对于返回参数表忽略 join,joinAll,joinEx 的相关设置�?
## string.args 成员列表

用于安全地合成命令行参数�?
解析命令行参数请使用�?string.cmdline

创建进程启动参数表对象�?
返回参数表可自动合成 process 库所有启动进程函数的命令行参数�?
�?tostring 函数也可以将返回参数表转换为表示命令行参数的字符串�?
### string.args.escape("命令行参�?)

转义命令行参数�?
不在双引号内、且含空白字符或 ^ \| & 等字符的参数转义后置入双引号�?
关于命令行参数转义规则，请参�?string.cmdline 的说�?
### string.args.join

用于安全地合成命令行参数，并自动处理转义字符�?
注意 process.joinArguments 指向 string.args.join 函数�?
这两个函数实际为同一个函数�?
### string.args.join(args,...)

可传入一个参数表（可包含数组成员）或多个�?null 参数�?
如果传入参数是一个表对象（可包含数组），

参数表将自动合并为单个命令行参数并返回一个字符串值�?
表中以键名以 \- �?/ 开头的名值对自动合并为命令行参数�?
数组成员也会合并到命令行，但名值对参数总是置于数组参数之前�?
如果数组成员也是表对象，则仍调用此函数直接转换为字符串（不再转义）�?
其他数组或命名参数值用 tostring 转换为字符串，按需添加引号进行必要的转义�?
不在双引号内、且含空白字符或 ^ \| & 等字符的参数转义后置入双引号�?
如果传入的命令行参数为单个字符串参数，不作任何转换直接返�?
### string.args.joinAll

用于安全地合成命令行参数，并自动处理转义字符�?
### string.args.joinAll(args,...)

可传入一个参数表（可包含数组成员）或多个�?null 参数�?
如果传入参数是一个表对象（可包含数组），

参数表将自动合并为单个命令行参数并返回一个字符串值�?
表中以键名以 \- �?/ 开头的名值对自动合并为命令行参数�?
此函数与 string.args.join 函数的主要区别：

�?/，\- 前导符的参数名由小驼峰转为连字符风格并加 \-\- 前缀�?
数组成员也会合并到命令行，但名值对参数总是置于数组参数之前�?
如果数组成员也是表对象，则仍调用此函数直接转换为字符串（不再转义）�?
其他数组或命名参数值用 tostring 转换为字符串，按需添加引号进行必要的转义�?
不在双引号内、且含空白字符或 ^ \| & 等字符的参数转义后置入双引号�?
如果传入的命令行参数为单个字符串参数，不作任何转换直接返�?
### string.args.joinEx

用于安全地合成命令行参数，并自动处理转义字符�?
相比 join �?joinAll�?
joinEx 可用参数@1 自定义是否转换驼峰参数名为连字符格式�?
可用参数 @2 自定义表类型参数的名值对分隔�?
### string.args.joinEx(dashCase,separator,boolean,args,...)

参数 @args 开始可传入一个参数表（可包含数组成员）或多个�?null 参数�?
如果 @args 参数是一个表对象（可包含数组），

参数表将自动合成为单个命令行参数并输出一个字符串值�?
表中以键名以 \- �?/ 开头的名值对自动合成为命令行参数�?
如果参数 @dashCase �?true，其他无前导符的参数名自驼峰转连字符风格后合成命令行�?
数组成员也会合并到命令行，但名值对参数总是置于数组参数之前�?
如果数组成员也是表对象，则仍调用此函数直接转换为字符串（不再转义）�?
其他数组或命名参数值用 tostring 转换为字符串，按需添加引号进行必要的转义�?
不在双引号内、且含空白字符或 ^ \| & 等字符的参数转义后置入双引号�?
可选用参数 @Separator 自定义表类型参数的名值对分隔符，默认为空格�?
参数 @boolean 如果恒等�?false，则值恒等于 true 的参数仅保留参数名�?
如果传入的命令行参数为单个字符串参数，不作任何转换直接返�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/string/args.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/string/args.md')
