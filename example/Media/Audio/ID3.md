[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: ID3 标签

```aardio aardio
//ID3 标签
import console;
import fsys.tagLib;
import fsys.dlg;

var mp3Path = fsys.dlg.open("*.mp3|*.mp3");
if(!mp3Path) return;

var tagFile = fsys.tagLib(mp3Path);
console.dumpJson(tagFile);

for name,value in tagFile.each(){
    console.log(name,value);
}

console.log(tagFile.title);
console.pause(true);

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Media/Audio/ID3.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Media/Audio/ID3.md')

