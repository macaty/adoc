[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# web.script.yaml 库模块帮助文�?
## web.script.yaml 成员列表

YAML 解析器（基于 js-yaml �?
### web.script.yaml.dump

生成 YAML，返�?YAML 文本

### web.script.yaml.dump(object,option)

参数 @object 指定 aardio 表对象�?
参数 @option 可选用一个表指定选项�?
具体选项请参�?js-yaml 文档，一般可省略

### web.script.yaml.load

解析单文�?YAML，解析结果输出为 aardio 表对�?
### web.script.yaml.load(yamlText,option)

参数 @yamlText 指定 YAML 文本�?
参数 @option 可选用一个表指定选项�?
具体选项请参�?js-yaml 文档，一般可省略

### web.script.yaml.loadAll

解析多文�?YAML，解析结果输出为 aardio 数组对象

### web.script.yaml.loadAll(yamlText,option)

参数 @yamlText 指定 YAML 文本�?
参数 @option 可选用一个表指定选项�?
具体选项请参�?js-yaml 文档，一般可省略

### web.script.yaml.loadFile

解析单文�?YAML 文件，解析结果输出为 aardio 表对�?
### web.script.yaml.loadFile(path,option,all)

参数 @path 指定 YAML 文件路径�?
参数 @option 可选用一个表指定选项�?
具体选项请参�?js-yaml 文档，一般可省略�?
参数 @all �?true 则作为多文档 YAML 解析�?
省略参数 @all则默认作为单文档 YAML 解析�?
### web.script.yaml.saveFile

生成 YAML 并保存到文件

### web.script.yaml.saveFile(path,object,option)

参数 @path 指定要保存的文件�?
参数 @object 指定 aardio 表对象�?
参数 @option 可选用一个表指定选项�?
具体选项请参�?js-yaml 文档，一般可省略

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/web/script/yaml.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/web/script/yaml.md')

