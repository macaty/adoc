[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 批处理与 aardio 对比 - for 命令之遍历文�?
```aardio aardio
//批处理与 aardio 对比 - for 命令之遍历文�?import console;
import process.batch;

//批处�?for 遍历一个目录下的所有文�?var bat = process.batch(`
@for /r "./" %%I in (*) do @echo %%I
`)

for( all,out,err in bat.each() ){
    console.log(all)
}

console.more(1);

/*
aardio 遍历一个目录上的所有文�?*/
import fsys;
fsys.enum( "/", "*.*",
    function(dir,filename,fullpath,findData){
        if(filename){
            console.log("发现文件�?+filename,"完整路径�?+fullpath)
        }
        else{
            console.log( "发现目录�? + dir )
        }
    }
    ,/*如果此参数为false则忽略子目录*/
);

console.pause()

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Bat/Bat aardio对比/for.fsys.md)

