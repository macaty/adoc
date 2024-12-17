[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# string.lrc 库模块帮助文�?
## string 成员列表

### string.lrc

歌词解析

### string.lrc( 歌词文本 )

创建歌词解析�?
### string.lrc()

[返回对象:stringLrcObject](#stringLrcObject)

## stringLrcObject 成员列表

### stringLrcObject.each()

```aardio aardio
for( line,ms in stringLrcObject.each() ){
    io.print( line,ms );/*按时间索引排序遍历所有歌�?/
}

```

### stringLrcObject.find

查找歌词位置

### stringLrcObject.find(当前时间)

返回开始索�?结束索引,歌词持纪时间

开始索引与结束索引不同则应显示多行歌词

时间以毫秒为单位

失败返回空�?
### stringLrcObject.findLrc

查找歌词

### stringLrcObject.findLrc(当前时间)

返回歌词,歌词持续时间

时间以毫秒为单位

失败返回空�?
### stringLrcObject.index

当前歌词索引

### stringLrcObject.lyric

歌词按时间排序后的数�?
每个歌词为一个数�?索引1为显示时�?索引2为歌�?
### stringLrcObject.offset

歌词提前时间

负数表示延后

### stringLrcObject.stringify()

重新生成歌词并返回字符串

重复歌词将自动合并时间标�?并自动修正不规范格式

### stringLrcObject.tags.al

album

唱片�?专辑�?
### stringLrcObject.tags.ar

artist

歌手、演唱�?
### stringLrcObject.tags.by

by ...

LRC文件制作�?
### stringLrcObject.tags.re

player/editor

创建此LRC文件的程�?
### stringLrcObject.tags.ti

title

歌词标题

### stringLrcObject.tags.ve

version

程序的版�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/string/lrc.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/string/lrc.md')

