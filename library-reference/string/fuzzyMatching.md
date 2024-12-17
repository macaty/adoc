[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# string.fuzzyMatching 库模块帮助文�?
## string 成员列表

### string.fuzzyMatching

模糊匹配字符�?
创建字符串模糊匹配对�?
### string.fuzzyMatching()

[返回对象:stringFuzzyMatchingObject](#stringFuzzyMatchingObject)

### string.fuzzyMatching(strTemplte,charPattern,method)

创建模糊匹配对象�?
strTemplte 参数指定需要匹配的模板字符串�?
charPattern 为可选参数，用模式匹配语法指定提取待比较字符的模式串�?
method 为可选参数，可选指定以下算法：

- fuzzyMatching 相似度算法，关注字符频率，首尾连续性敏感�?
- n 此参数用数值指定比较单元字数则使用 N-gram 算法，局部连续性敏感，效果较好，速度最快�?
- levenshtein 准确度高，对字符位置敏感 ，较慢�?
- cos 考虑了字符频率，不关注顺序�?
- jaccard 只考虑字符是否出现�?
## stringFuzzyMatchingObject 成员列表

### stringFuzzyMatchingObject.find(匹配字符串数�?最小相似度)

在文本数组中查找最接近的字符串

最小相似度为可选参�?默认值为 0.6,

成功则返回值@1为找到的文本,

返回值@2为相似度（小�?最大相似为1,不相似为0�?

返回�?@3 为匹配索�?

无匹配则返回 null

### stringFuzzyMatchingObject.match(匹配字符�?

返回文本相似�?
相似度为小数,最大相似为1,不相似为0

比较规则为先比较相同字符�?

然后再自左侧或右侧查找相同的最长字符串

### stringFuzzyMatchingObject.search(字符�?最小相似度)

模糊检测参数传入的字符串是否包含模板字符串

最小相似度默认�?0.8

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/string/fuzzyMatching.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/string/fuzzyMatching.md')

