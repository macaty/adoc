[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 文件读写

```aardio aardio
//文件读写
import console;
import inet.ftp;

console.log("正在连接")
ftp = inet.ftp("服务器IP","用户�?,"密码");
if(!ftp){
    console.log("请输入正确的服务器参�?);
    console.pause();
    return;
}

//显示当前目录
console.log( ftp.getCurDir() )

//关闭服务器UTF8编码
ftp.command("OPTS UTF8 off")

file = ftp.open("/目录/文件�?txt","wb")

//支持文件流方式上传数�?使用循环即可控制上传进度
file.write("写数�?,"写更多数�?,'\r\n')
file.write("写数�?,"写更多数�?,'\r\n')

ftp.close();
console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Network/inet/ftp/ftp.file.md)

