[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 英文单词�?
```aardio aardio
import console;
import string.words;

/*
《模匹匹配快速入门�?https://www.aardio.com/zh-cn/doc/guide/language/pattern-matching.html
*/

for(k,v in string.words){

    //查找 r 开头，与“人”有关的名词
    if( string.find(k,"^r")
        && string.find(v,"!\wn\..*�?*")
    ){
        console.log(k,v);
        console.more(20);
    }
}

console.pause(true);

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Text/words.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Text/words.md')

