[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: fsys.config

```aardio aardio
//fsys.config
import console;
import fsys.config;

//写入配置文件
var cfgPath = io.appData("/aardio/test.fsys.config");
var cfg = fsys.config(cfgPath)
cfg.配置文件�?字段�?= {
    a = 123;
    b = "字符�?
}

//读取配置文件
var cfgPath = io.appData("/aardio/test.fsys.config");
var cfg = fsys.config(cfgPath)
console.dumpJson( cfg.配置文件�?)

console.pause()

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/File/Config/fsys.config.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/File/Config/fsys.config.md')

