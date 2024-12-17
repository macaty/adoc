[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: COM 鎺ュ彛 - 鍒涘缓瀵硅薄

```aardio aardio
//COM 鎺ュ彛 - 鍒涘缓瀵硅薄
import com;
import console;

//鍙傝�冩枃妗ｏ細 https://www.aardio.com/zh-cn/doc/library-guide/builtin/com/com.html
//鍒涘缓 COM 瀵硅薄锛屾敞鎰?COM 鏈夊叧鐨勫嚱鏁伴�氬父棣栧瓧姣嶅ぇ鍐?var fs = com.CreateObject("Scripting.FileSystemObject");

//浣跨敤 COM 瀵硅薄
var dir = fs.GetFolder( io.fullpath("/") );

//閬嶅巻COM瀵硅薄鎴愬憳
for index,file in com.each(dir.Files) {
    console.log(file.path);
}
console.more();

//鏌ョ湅 COM 瀵硅薄鎴愬憳
console.dump( com.DumpTypeInfo(dir) );

//涓婇潰鐨勫嚱鏁板彲浠ョ畝鍐欎负
console.dump( dir );

//杈撳嚭鏇磋缁嗙殑 COM 瀵硅薄绫诲瀷搴撲俊鎭?import com.tlbDoc;
com.tlbDoc.dump( dir );//鐢?com.tlbDoc(dir) 鍙互寰楀埌杈撳嚭鐨勬枃妗?
console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/COM/GettingStarted/CreateObject.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/COM/GettingStarted/CreateObject.md')

