[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 文本分句

```aardio aardio
//文本分句
//使用指南: https://www.aardio.com/zh-cn/doc/library-guide/builtin/string/segmentation.html#sentences

var text = /*
例如这句要独立成句：“分句算法需要能够识别并处理各种标点符号，包括逗号、句号、感叹号等。�?“这是引号包含的内容�?类似这样的句子也要独立成句�?
英文缩写，前后引用，多重引号�?
"It's amazing!" he said. "I can't believe it."
What is the use of ''say,'' ''said'', and ''says''?

考虑各种松散写法。。。。�?考虑各种写法！！�?
考虑这种嵌套包含的引号：“这里面又有一层相同的“引号”，要正确处理这种对称匹配的引号”�?*/

import string.sentences;
for( i,v in string.sentences(text) ){
    print(v);
    thread.delay(300);
}

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Text/sentences.md)

