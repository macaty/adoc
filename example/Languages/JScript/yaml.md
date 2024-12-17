[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: YAML 解析

```aardio aardio
//YAML 解析
import console;
import web.script.yaml;

//局部变�?yaml 指向 web.script.yaml 名字空间
var yaml = web.script.yaml;

/*
YAML 快速入�?https://quickref.me/zh-CN/docs/yaml.html
https://learnxinyminutes.com/docs/zh-cn/yaml-cn
*/
var yamlText = /*
YAML: YAML Ain't Markup Language�?
What It Is:
  YAML is a human-friendly data serialization language.

*/

//解析 YAML 格式文本L，读取多文档 YAM�?var object = yaml.loadAll(yamlText)

//�?aardio 对象转换�?YAML 字符串�?var yamlText = yaml.dump(object);

//在控制台�?JSON 格式显示对象
console.dumpJson(object);

console.pause();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/JScript/yaml.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/JScript/yaml.md')

