[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: FTP 入门

```aardio aardio
//FTP 入门
import console;
import inet.ftp

console.log("正在创建ftp连接")
var ftp = inet.ftp("ftp.sjtu.edu.cn");

if(!ftp){
    console.log( inet.lastResponse() );
    console.pause();
    return;
}

//列出目录下的文件
for(dir,file,findData in ftp.eachDir("\")){
     console.log(  dir,file : "目录" );
}

for(dir,file,findData in ftp.eachDir("\arkhy")){
     console.log(  dir,file : "目录" );
}

//下载文件
if( ftp.download("\本地文件.txt","\arkhy\updata.txt") ){
     console.log(  dir,file : "目录" );
}

ftp.close();
console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Network/inet/ftp/inet.ftp.md)

