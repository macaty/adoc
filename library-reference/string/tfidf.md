[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# string.tfidf 库模块帮助文�?
## string 成员列表

### string.tfidf

用于计算 TF-IDF 词频�?
相关库： string.bm25

创建 TF-IDF 对象

### string.tfidf()

[返回对象:stringTfidfObject](#stringTfidfObject)

### string.tfidf(keywords)

创建 TF-IDF 对象�?
可选用一个字符串数组限定要计数的全部关键词�?
不指定则计算所有出现的分词

## stringTfidfObject 成员列表

### stringTfidfObject.addDocument

添加文档数据

### stringTfidfObject.addDocument(idOrPath,words)

添加文档数据�?
idOrPath可指定任何可作为键名的标识，可指定文档路径�?
words 指定文档内容分词后的字符串数组，

可用 mmseg 扩展库分词�?
### stringTfidfObject.calc

计算或重新计�?TF-IDF �?
### stringTfidfObject.calc(lengthNormFactor,tfLogBase,minDocLength)

在添加所有文档后可调用此函数计算或重新计�?TF-IDF 值�?
lengthNormFactor 用来调整文档长度归一化的影响程度，默认为 1�?
lengthNormFactor 越小文档长度归一化的影响就越小�?
简单说 lengthNormFactor 越低，短文档的权重和价值就越低�?
tfLogBase 用于控制 TF 计算中对数变换的底数，默认为 math.e�?
较小的底数会使得高频词的权重增长更加缓慢�?
它的作用是减少单个文档中频繁出现的词的影响�?
避免某些常见词在文档中的过度表示�?
使得更有意义的、但出现频率较低的词也能得到合理的权重�?
minDocLength 可选用于指定最小文档长度（分词数目，非字数）�?
默认值为 0，小�?minDocLength 的过短文档将会抑制其权重�?
### stringTfidfObject.getKeywords

调用 tfidf 函数后获取文档统计的关键词数组，�?TF-IDF 值排序�?
### stringTfidfObject.getKeywords(idOrPath,topN,excludePatterns,excludeWords)

idOrPath 参数指定文档标记（例如路径）�?
数组�?TF-IDF �?排序，TF-IDF 值较高的在前�?
可选用 topN 参数限定返回数组长度�?
可选通过 excludePatterns 参数使用一个模式串数组指定要排除的词�?
可选用 excludeWords 参数指定一个要排除的关键词表，键为要排除的�?
### stringTfidfObject.getScore

计算关键词在指定文档中的权重�?
### stringTfidfObject.getScore(keywords, idOrPath,decimals)

计算关键词在指定文档中的权重�?
keywords 参数指定关键词数组�?
idOrPath 参数指定文档标志，通常为路径�?
第一个返回值为计算得到的总权重，

第二个返回值为对应关键词顺序的权重数组�?
可选用 decimals 参数限定返回数组中权重的小数位数

### stringTfidfObject.search

搜索文档

### stringTfidfObject.search(keywords,topN)

搜索文档�?
keywords 指定要搜索的关键词数组�?
可选用 topN 参数限定返回的文档数目上限�?
返回的到的文档数组，按权重排序�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/string/tfidf.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/string/tfidf.md')

