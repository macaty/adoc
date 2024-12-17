[aardio 鏂囨。](../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 瑁佸壀鍥惧儚

```aardio aardio
//瑁佸壀鍥惧儚
import gdip.path;
import gdip.bitmap;
import gdip.graphics;

//鍔犺浇鍥惧儚
var srcImage = gdip.bitmap("C:\Users\jacen\Desktop\abc.png");

//鍒涘缓杈撳嚭鍥惧儚
var destImage = gdip.bitmap(srcImage.width, srcImage.height);

//鍒涘缓鐢绘澘
var graphics = destImage.getGraphics();

//鍒涘缓璺緞
var path = gdip.path();

//鎸囧畾瑕佽鍓殑 4 涓偣锛屾敮鎸佷笉瑙勫垯褰㈢姸銆?path.addPolygon({
    {20,20},
    {100,100},
    {100,300},
    {20,300}
});

//璁剧疆瑁佸壀璺緞
graphics.setClipPath(path);

//缁樺浘
graphics.drawImage(srcImage, 0, 0);

//淇濆瓨杈撳嚭鍥惧儚
destImage.save("/瑁佸壀鍚庣殑鍥惧儚.png");

//閲婃斁瀵硅薄
path.delete();
graphics.delete();
srcImage.dispose();
destImage.dispose();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Graphics/setClipPath.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Graphics/setClipPath.md')

