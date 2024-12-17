[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# color.table 库模块帮助文�?
## color 成员列表

### color.table()

创建色表,用于color.view,

返回常用标准色组成的数组,

每个数组成员由色彩中文名、英文名、RGB�?个元素组�?
## color.table 成员列表

### color.table.analogousColor(clr,gdi)

创建类似色表,

类似色是在色相环上邻近的颜色,会给人带来和谐、舒服的视觉效果,

参数@1使用ARGB格式颜色值指定主�?如果颜色为gdi的rgb格式请将参数@2指定为true

### color.table.complementaryColor(clr,gdi)

创建补色�?

突出对比效果,

参数@1使用ARGB格式颜色值指定主�?如果颜色为gdi的rgb格式请将参数@2指定为true

### color.table.find()

参数@1指定一个ARGB格式颜色数�?

在色表中查找并返回色卡信�?
### color.table.init()

净色彩数组转换为color.table标准格式

### color.table.insert(clrTable,clrInfo,index)

在参数@1指定的色表中添加色卡,

clrInfo必须是一个数�?索引1放成员名,索引2放英文名,索引3放RGB格式颜色数�?
可选用参数@3指定插入位置,默认添加到尾�?
### color.table.lightColor(clr,gdi)

创建亮度色表,

色相不变,亮度�?%�?%的变化色�?

参数@1使用ARGB格式颜色值指定主�?如果颜色为gdi的rgb格式请将参数@2指定为true

### color.table.monochromaticColor(clr,gdi)

创建单色调方�?

单色调是色相不变,但亮度发生变化的配色方案,

参数@1使用ARGB格式颜色值指定主�?如果颜色为gdi的rgb格式请将参数@2指定为true

### color.table.splitComplementaryColor(clr,gdi)

创建分散补色�?

对比�?但比补色降低了对比强�?
即有较好的对比效�?也不会显得太突兀,

参数@1使用ARGB格式颜色值指定主�?如果颜色为gdi的rgb格式请将参数@2指定为true

### color.table.squareColor(clr,gdi)

创建矩形色表,

在色相环上平均分�?并组成两对互补色,

色彩丰富,要注意选定主色,处理好色彩间的平�?
参数@1使用ARGB格式颜色值指定主�?如果颜色为gdi的rgb格式请将参数@2指定为true

### color.table.tetradicColor(clr,gdi)

创建四色�?

由两对在色相环上的互补色组成,色彩丰富,

但要注意选定主色,处理好色彩间的平�?
参数@1使用ARGB格式颜色值指定主�?如果颜色为gdi的rgb格式请将参数@2指定为true

### color.table.triadicColor(clr,gdi)

创建三色�?

三色在色相环上平均分�?应当用一个做主色,处理好色彩间的平�?
参数@1使用ARGB格式颜色值指定主�?如果颜色为gdi的rgb格式请将参数@2指定为true

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/color/table.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/color/table.md')

