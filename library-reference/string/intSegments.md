[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# string.intSegments 库模块帮助文�?
## string 成员列表

### string.intSegments()

解析参数@1指定的整数列�?

并返回数值从小到大排序后的数�?

参数@1可以指定单个数�?或用文本指定多个数�?

文本中数值用逗号分隔,允许�?\- 指定数值区�?

例如�?6881-6889,6999",

参数@1传入非文本非数值参数返�?null

## string.intSegments 成员列表

用于解析文本格式的整数列�?支持区间表示�?
### string.intSegments.each(str)

```aardio aardio
for i,num in string.intSegments.each(""){
    /*调用 string.intSegments 解析字符串获得数值数�?
并遍历该数组*/
}

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/string/intSegments.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/string/intSegments.md')

