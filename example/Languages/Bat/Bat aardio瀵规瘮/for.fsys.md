[aardio 鏂囨。](../../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鎵瑰鐞嗕笌 aardio 瀵规瘮 - for 鍛戒护涔嬮亶鍘嗘枃浠?
```aardio aardio
//鎵瑰鐞嗕笌 aardio 瀵规瘮 - for 鍛戒护涔嬮亶鍘嗘枃浠?import console;
import process.batch;

//鎵瑰鐞?for 閬嶅巻涓�涓洰褰曚笅鐨勬墍鏈夋枃浠?var bat = process.batch(`
@for /r "./" %%I in (*) do @echo %%I
`)

for( all,out,err in bat.each() ){
    console.log(all)
}

console.more(1);

/*
aardio 閬嶅巻涓�涓洰褰曚笂鐨勬墍鏈夋枃浠?*/
import fsys;
fsys.enum( "/", "*.*",
    function(dir,filename,fullpath,findData){
        if(filename){
            console.log("鍙戠幇鏂囦欢锛?+filename,"瀹屾暣璺緞锛?+fullpath)
        }
        else{
            console.log( "鍙戠幇鐩綍锛? + dir )
        }
    }
    ,/*濡傛灉姝ゅ弬鏁颁负false鍒欏拷鐣ュ瓙鐩綍*/
);

console.pause()

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Bat/Bat aardio瀵规瘮/for.fsys.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Bat/Bat aardio瀵规瘮/for.fsys.md')

