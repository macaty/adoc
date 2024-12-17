[aardio 鏂囨。](../../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: FTP 鍏ラ棬

```aardio aardio
//FTP 鍏ラ棬
import console;
import inet.ftp

console.log("姝ｅ湪鍒涘缓ftp杩炴帴")
var ftp = inet.ftp("ftp.sjtu.edu.cn");

if(!ftp){
    console.log( inet.lastResponse() );
    console.pause();
    return;
}

//鍒楀嚭鐩綍涓嬬殑鏂囦欢
for(dir,file,findData in ftp.eachDir("\")){
     console.log(  dir,file : "鐩綍" );
}

for(dir,file,findData in ftp.eachDir("\arkhy")){
     console.log(  dir,file : "鐩綍" );
}

//涓嬭浇鏂囦欢
if( ftp.download("\鏈湴鏂囦欢.txt","\arkhy\updata.txt") ){
     console.log(  dir,file : "鐩綍" );
}

ftp.close();
console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Network/inet/ftp/inet.ftp.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 服务器报告访问的文件是隐藏的。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Network/inet/ftp/inet.ftp.md')

