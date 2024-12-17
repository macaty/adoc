[aardio 鏂囨。](../../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鏂囦欢璇诲啓

```aardio aardio
//鏂囦欢璇诲啓
import console;
import inet.ftp;

console.log("姝ｅ湪杩炴帴")
ftp = inet.ftp("鏈嶅姟鍣↖P","鐢ㄦ埛鍚?,"瀵嗙爜");
if(!ftp){
    console.log("璇疯緭鍏ユ纭殑鏈嶅姟鍣ㄥ弬鏁?);
    console.pause();
    return;
}

//鏄剧ず褰撳墠鐩綍
console.log( ftp.getCurDir() )

//鍏抽棴鏈嶅姟鍣║TF8缂栫爜
ftp.command("OPTS UTF8 off")

file = ftp.open("/鐩綍/鏂囦欢鍚?txt","wb")

//鏀寔鏂囦欢娴佹柟寮忎笂浼犳暟鎹?浣跨敤寰幆鍗冲彲鎺у埗涓婁紶杩涘害
file.write("鍐欐暟鎹?,"鍐欐洿澶氭暟鎹?,'\r\n')
file.write("鍐欐暟鎹?,"鍐欐洿澶氭暟鎹?,'\r\n')

ftp.close();
console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Network/inet/ftp/ftp.file.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 服务器报告访问的文件是隐藏的。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Network/inet/ftp/ftp.file.md')

